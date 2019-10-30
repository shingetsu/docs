# Apache連携

Windowsでの朔とApacheの連携方法

## はじめに

Windowsで朔とApacheを連携させる方法です。

これは管理者向けの情報です。通常、朔とApacheを連携させる必要はありません。

これはApacheを運用している（ために、朔に80番ポートが使えない）人向けの情報です。そのような場合以外で、朔のURLからポート番号を消したい場合はsaku.iniでport: 80とするのが簡単です。

## 前提

朔共通版は c:\saku に

Apache は c:\apache にあるものと仮定します。

また、PCのドメインは bbs.example.com

PCのプライベートアドレスは 192.168.1.2 だと仮定します。

ここでは朔は共通版を”インストール”せずに使うことを前提に話を進めます。

## 確認

まずは、朔、Apacheが正常に動いていることを確認してください。

ここでは朔は http://localhost:8000/ Apacheは http://localhost/ でアクセスできるものとします。

## Apacheの設定

Apacheのhttpd.confがあるフォルダ（c:\apache\conf）に以下の内容でshingetsu.confを作ってください。

aclファイルはサンプルをc:\saku\file\acl.sampleからc:\apache\confにコピーしてください。

ServerAdminは原則、有効なメールアドレスにしましょう。

    <VirtualHost *>
       ServerAdmin webmaster@bbs.example.com
       DocumentRoot c:/apache/htdocs/shingetsu
       ServerName bbs.example.com
       ServerAlias bbs.example.com
       ErrorLog logs/shingetsu.error.log
       CustomLog logs/shingetsu.access.log combined
       RewriteMap escape int:escape
   
       <Directory "/">
           <Limit POST>
               Include conf/acl.sample
           </Limit>
       </Directory>
   
       <Directory "c:/apache/htdocs/shingetsu">
           Options -Indexes -ExecCGI
           AddType text/xml;charset=UTF-8 .rdf
           RewriteEngine on
           RewriteRule gateway.cgi/rss rss.rdf
           RewriteRule server.cgi - [F]
           RewriteRule ^([^/]*).js$ /STATIC/$1.js
           RewriteRule ^([^/]*).css$ /STATIC/$1.css
           RewriteRule favicon.ico /STATIC/favicon.ico
           RewriteRule rss1.xsl /STATIC/rss1.xsl
           RewriteRule ^thread.cgi/(thread_[0-9A-F]*)/([0-9a-f]*)/([0-9]*).(.*) \
                       /CACHE/$1/attach/$3_$2.$4
           <IfModule mod_proxy.c>
               RewriteRule gateway.cgi(.*) \
                   http://192.168.1.2:8000/gateway.cgi${escape:$1} [P,NE]
               RewriteRule thread.cgi(.*) \
                   http://192.168.1.2:8000/thread.cgi${escape:$1} [P,NE]
           </IfModule>
       </Directory>
   
       Alias /STATIC/ c:/saku/www/
       <Directory "c:/saku/www/">
           Options -Indexes -ExecCGI
       </Directory>
   
       Alias /CACHE/ c:/saku/cache/
       <Directory "c:/saku/cache/">
           Options -Indexes -ExecCGI
       </Directory>
    </VirtualHost>

httpd.confに次の４行を追加してください。

    LoadModule proxy_module modules/mod_proxy.so
    LoadModule proxy_http_module modules/mod_proxy_http.so
    LoadModule rewrite_module modules/mod_rewrite.so
    Include conf/shingetsu.conf

ここまでできたなら、Apacheを再起動させてください。次のURLにアクセスできるでしょうか？

http://bbs.example.com/gateway.cgi

接続がタイムアウトする場合、c:\windows\system32\drivers\etc\hostsに次の一文を追加してみてください。

    127.0.0.1 bbs.example.com

## mkrss.pyを使う

朔共通版に付属するmkrss.pyでindex.html、rss.rdfを生成します。

（手順がややこしいです。またWindowsのサービスに関する知識が必要になります）。

（Pythonはインストール済みであるとします）。

c:\apache\htdocsにshingetsuというフォルダを作成してください。

c:\saku\tool\mkrss.pyをc:\sakuにコピーしてください。

c:\saku\file\saku.iniに次の６行を追加してください。
    [Path]
    cache_dir: c:/saku/cache
    apache_docroot: c:/apache/htdocs/shingetsu
    [Gateway]
    server_name: bbs.example.com
    proxy_destination: 192.168.1.2:8000

mkrss.pyを実行します。間違いがなければこれでc:\apache\htdocs\shingetsuに index.html、rss.rdf他が生成されます。

http://bbs.example.com/ にアクセスできるか確認してください。

## 自動実行の設定
通常、ゲートウェイとして機能させるにはこのmkrss.pyを10分間隔くらいで自動実行させる必要があります。

ここでは[cronNT](http://www.vector.co.jp/soft/winnt/util/se232096.html)というフリーソフトを使うことにします（このような自動実行させるソフトはいくつかあります）。

はじめにmkrss.pyを実行させるためのバッチファイルをつくります。以下の内容でc:\saku\mkrss.batを作ってください。

   cd c:\saku
    mkrss.py

次にReadme.txtに従ってcronNTをインストールしてください。

crontab.iniに次の１行を追加してください。

    */10 * * * * c:\saku\mkrss.bat

この後cronNTを起動（又は再起動）させます。cronNTのReadme.txtに従ってください。

## さいごに
これですべての作業は完了しました。お疲れさまでした。

## 参考
[Apacheと朔を組み合わせて使う方法](http://shingetsu.info/manage/apache)
