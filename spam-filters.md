# スパムフィルタ倉庫

## スパムフィルタを共有しよう
みんなの知恵を集めて、スパムを撃退しましょう。

## まずは初心者用
[初級スパムフィルタ](/spam-filters-elementary.md)へ…

## URLいっぱい書いてるヤツ
URLを10回以上書いてるとBANG!

    (https?://.+){10}.+

## メ欄にURL書いてるの
メ欄にURL貼ってきてるヤツもウザイよね。（これは.comを指定）

    <>mail:http://.+\.com.*

## 上の2つの合わせ技
上の2つを合わせてみた。メ欄になにか書いてて、URLが5個以上。

    (https?://.+){5}.+<>mail:.+


- 全部設定する必要はないよ。今のところ、最後のやつ（合わせ技）だけで、あらかた落とせる感じ。
- 新手のが来たら、追加よろしく！

## 短いの
意味不明の短いメッセージが大量にきてました。

    \.txt\;.+\;.+<>mail:.+<>name:

## セールスのスパム
セールスのスパムについて、特定のキーワードが3回以上あると引っ掛かるというフィルタを考えてみました。また、必ず名前とメールアドレスが付いているので、それも条件にしています。

    ((ticket|jewel|free|gold|platinum|silver).*){3}<>mail:.+\.com.*<>name:

## いろいろ

    <>mail:[^@]+@[^.]+\..+
    <br> &lt;a href="
    \[url=http://
    #<br>(http://.+){5}<br>
    <>body:plime-keys.txt;5;10<>mail:
    (http://.+){10}.+
    (http://.+){5}.+<>mail:.+
    <>mail:mail
    <>body:doors
    (Casino.+){5}.+
    (kanpoulife.com.+){2}.+
    https?://.+<>mail:.+\.com.*<>name:
    <>mail:.+@(gmail|aol)\.com<>name:
    http://.+<>mail:.+yahoo\.cn<>name:
    <>mail:.*Dr.*@.*\.com<>name:.*Dr

## 2012/01/07公開　スパムがあらかたはじけるセット
    (https?://.+){5}.+
    href.*http
    [^(\>|\:|＞)]\ http

- ２ヶ月程度の過去ログを見る限りはじけています。

## 手で消す時用
 「新月の開発」スレから転載。考えてくれた人サンクス！
（使い方は次のリンクの、2.プログラムコードが直接書かれている場合を参照のこと
https://d.hatena.ne.jp/keyword/%A5%D6%A5%C3%A5%AF%A5%DE%A1%BC%A5%AF%A5%EC%A5%C3%A5%C8）

    チェックボックスを全部チェックするブックマークレット
    javascript:(function(){c=document.getElementsByTagName("input");for(i=0;i<c.length;i++){c[i].checked=true;}}())

    チェックボックスのチェックしたものとチェックしたものの間だけチェックするブックマークレット
    （言ってて意味分からん……。チェックとチェックで範囲指定するってことね）。
    javascript:(function(){c=document.getElementsByTagName("input");cc=false;for(i=0;i<c.length;i++){if(c[i].checked){if(cc){cc=false;}else{cc=true;}}if(cc){c[i].checked=true;}}}()) 
