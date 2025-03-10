# 新月ハンドブック(仮)

新参者向けのドキュメントだよ。


## 新月とは
新月とは不特定多数のコンピューターを直接接続してひとつの掲示板を構築するシステムです。またシステムが提供する掲示板サービスも新月と呼びます。

新月は現在、朔(さく) https://shingetsu.info/saku/ というソフトウェアを稼動させることで掲示板ネットワークとサービスを提供しています。

- [新月の紹介](https://shingetsu.info/intro/)
- [Wikipedia](https://ja.wikipedia.org/wiki/%E6%96%B0%E6%9C%88_%28%E6%8E%B2%E7%A4%BA%E6%9D%BF%29)

### 新月の特徴
新月の特徴は **不特定多数のコンピューターを直接接続する技術を用いて掲示板サービスを提供する** ことです。
不特定多数のコンピューターを接続する技術をP2P ( ピーツーピー / ピアツーピア ) と呼びます。

通常の掲示板のように特定の(人が管理する)コンピューターにアクセスして利用するという掲示板ではありません。(実際は公開ゲートウェイと呼ばれる特定のコンピューターにアクセスして投稿することができます)

新月用通信ソフト (朔、 NanaSHI など) が不特定多数のコンピューターを繋ぎ、掲示板への書き込みを新月ネットワーク全体へ伝播させます。ユーザはいつでも書き込み、閲覧できますが、だれがどこから書き込んだのか知ることは困難で、 匿名性が高い掲示板 (発言者の身元が特定しにくいということ。絶対に特定できないわけではない。) になっています。

参考ページ https://shingetsu.info/tutorial/original


### 新月の利用方法
- [新月初心者の館 - チュートリアル](/tutorial.md)

#### 意見交換の場として
一般的な意見交換の場として新月(掲示板)を利用することができます。新月用通信ソフトは必要ありません。普段お使いのウェブブラウザ(IEやFirefox)から発言できます。

掲示板の利用は公開ゲートウェイを使用します。ただし他人のコンピューターを経由して掲示板を利用することになるので匿名性の点では弱いです。

2025 年 2 月現在、安定して運用されている公開ゲートウェイ

- https://bbs.shingetsu.info/
- https://bbs.rep4649.freemyip.com/

どれを使ってもかまいませんが、一部の機能が制限されている公開ゲートウェイがあります(ゲートウェイとして動作している **朔** という新月ネットワークを構築するソフトウェアを自分のコンピューターにインストールすればすべての機能が使えます)。

#### 匿名掲示板として
新月用通信ソフトをあなたのパソコンで動かせば匿名性の高い掲示板として利用できます。この利用方法では、あなたは掲示板の利用者であり管理者でもあります。

新月用通信ソフトウェア **朔(さく)** を使う https://shingetsu.info/saku/

### 新月のメリット
新月は他の掲示板と比較して次のような利点があります。

- 資源を分散、共有するのでコンピューターの性能は二の次
- 資源の分散は権限の分散も意味します。このためデータ通信の隠匿性が高まります。

新月は専用の通信ソフトが稼働しているコンピューターで掲示板サービスを提供します。
この専用の通信ソフトは誰でも動かすことができます。あなたのパソコンで動くようにも設計されています。
特定の企業や団体によって運営される掲示板ではないので特定の権威者に依存せずにサービスが提供されるのです。

サービスの権限=通信ソフトの権限を不特定多数の人に分散させることで、掲示板の投稿データの保存やデータ通信に利用される資源が分散されるのでサービスの停止を低減できます。つまり参加するコンピューターが多いほど安定したサービスを供給できます。

新月の匿名性を上手に使えば発言を恐れることはありません。人に言えない悩みなど打ち明けることができるでしょう。あなたが恐れる者の検閲を回避することもできるのです。

### 新月のデメリット
- 資源が分散するため新月ネットワークの全体の管理が困難
- 課金方法(ビジネスモデル)が作りにくい?
- 参加するコンピューター(ノード数)が少なければメリットも台無し

## 新月の具体的な使い方
新月を掲示板として利用する方法を2つ紹介します。

### 意見交換の場として
「公開ゲートウェイ」と呼ばれるコンピューターにアクセスすれば掲示板への投稿が可能です。

「公開ゲートウェイ」は複数ありますのでどのゲートウェイを使っても構いません。ただしゲートウェイ毎に投稿できるスレッドが異なる場合があります。

基本的に公開ゲートウェイを利用する場合は **匿名性は確保されず、掲示板のスレッドを管理する権限はありません** 。公開ゲートウェイのサービス設定に依りますが、たいていの場合、(管理上の都合等で)新規スレッドの作成を許可していないなど、一部の機能が制限されています。


#### 公開ゲートウェイの使い方
公開ゲートウェイとは、新月を利用する誰にでも開かれたサーバーの事を指します。
公開ゲートウェイを利用すれば、新月用のソフトウェア( **朔** など)をインストールしなくても掲示板への投稿ができます。公開ゲートウェイの設定によっては新しいスレッドの作成を許可していることもありますが、基本的にはレス投稿専用のサーバーだと考えてください。

次のURLの一覧から適当なゲートウェイにアクセスしてください。

2025 年 2 月現在、安定して運用されている公開ゲートウェイ

- https://bbs.shingetsu.info/
- https://bbs.rep4649.freemyip.com/

「一覧」から興味のあるスレッドを探して発言してください。

また、とても重要なことですが、常時稼動して新月のネットワークを支えているサーバーが存在しないと掲示板データの共有がうまくいきません。公開ゲートウェイは常時稼動しているものなので、ゲートウェイの管理者に感謝しましょう。

### 匿名掲示板として
匿名性の高い掲示板として新月を利用するには、 **あなたのコンピュータが新月の一部を支えなければなりません** 。自分のコンピュータで新月に参加するために、専用のソフトウェアをインストールしてください。

現在は[朔(さく)](https://shingetsu.info/saku/)というソフトウェアが、新月への参加を可能にする唯一のソフトウェアです。

朔は常時動かしている必要はありません。あなたがコンピュータにログイン(サインイン)している間に起動していれば構いません。

#### 朔を使う
朔には1つのエディションがあります。

- **共通版** (Python スクリプト版) は別途 [Python](https://www.python.org) (3.9以降) をインストールして使うもので、WindowsでもUnixでも動きます。

#### ダウンロード
通常はこちらにある「安定版」をダウンロードしてください:
https://shingetsu.info/saku/

#### 起動
1. コマンドの実行
    - **共通版**: アーカイブを展開後、次のコマンドを実行: python saku.py
2. 閲覧
少し待って、 http://localhost:8000 を開いてみる。もし、ページが表示されなければ、TCP 8000番ポートを開ける。

#### 掲示板の管理
#### トラブルシューティング
#### ポートの開放
新月ネットワークはP2Pネットワークなので、本来、それに参加するにはあなたのコンピュータ（ここではPCと表記します）が一つのポート(通常はTCP8000番)を介してほかのノード(PC)から **直接** 接続可能でなければなりません。

あなたのPCのある環境にルータという機器がある場合、ポートを開ける必要のある場合があります。ルータには自動的にポートを開放する機能(UPnP機能 -- 注1)もあるので、設定の必要のないこともあります。

ルータを用いずにインターネットに直結しているコンピュータは、ファイアウォールなどで制限しない限り、朔をそのまま使えます。(プライベートIP割り当てのCATVインターネット回線を除く: [参考](https://www.akakagemaru.info/port/catv.html))

しかし、多くの場合は1本の接続(ADSL、光ファイバーなど)をルータを使って何台かのPCで共有しています。このような場合、あなたのPCはインターネットから隔てられたネットワーク(LAN)上にあるため、インターネット上の他のPCと **直接** 接続することができないのです。

それではなぜ普段ネットを見れるのか、ということについては参考サイトに譲ります。ポート開放では、大雑把に云えば、ルータが、特定のポートではあたかもあなたのPCが直接インターネットに繋がっているかのように見せかけることを行います(実際にはNAPTという方法が使われています)。

**ポートを開ける手順** としては、おおむね次のようなステップになります。
1. PCの現在のプライベートIPアドレス・サブネットマスク・デフォルトゲートウェイ(=ルータのIPアドレス)を調べる。
2. PCのIPアドレスを「自動的に取得」から固定のものにする
    - (1)で調べた値を入力。プライベートIPアドレスはメモっておく
    - 同時にDNSサーバーのIPも必要になる。デフォルトゲートウェイorプロバの書類に書いてあるor 208.67.222.222 208.67.220.220 ([OpenDNS](https://www.opendns.com))
    - 参考: [WindowsのIPアドレス固定する方法一覧](https://www.akakagemaru.info/port/ip-kotei.html)
3. ルータの設定画面に移る。各社設定方法は違うので、説明書を見るか[このサイト](https://www.akakagemaru.info/port/index.html)などを参考に。
4. 以下のようなNAPT(静的IPマスカレード)設定を追加する。
    - WAN側ポート: 8000-8000
    - プロトコル: TCP
    - 転送IPアドレス: &lt;(1)で調べて(2)で固定にしたプライベートIPアドレス&gt;
    - 転送ポート: 8000
5. ルータの設定を反映させたら完了！

- 参考1: https://www.akakagemaru.info/port/index.html
- 参考2: [ポート開放の確認](https://www.akakagemaru.info/port/tcpport.php)
- 注1(UPnP機能): ネットワーク(LAN)内のPCのソフトからの要求に応じて、ルータが自動的にポートの開放や情報更新を行う機能です。P2Pソフトとルータの両方が対応している必要があります。

### コンピュータ資源を提供する
### その他

## 新月の詳しい仕組み
- [書き込みすると何が起こるのか](https://shingetsu.info/manage/post)

## 管理者向けガイド
- [管理者向け情報](https://shingetsu.info/manage/)

### 掲示板の管理
### 朔のカスタマイズ

## 開発者になろう!
- JavaScriptやりたいなら https://shingetsu.info/extension/
- ノードを実装したいなら https://shingetsu.info/protocol/protocol-0.8.d1
- 連携ツール作るなら https://shingetsu.info/tech/cache とか https://shingetsu.info/saku/api
- [技術情報](https://shingetsu.info/tech/)

## 質問など
- [質問スレッド](https://bbs.shingetsu.info/thread.cgi/%e8%b3%aa%e5%95%8f%e3%82%b9%e3%83%ac%e3%83%83%e3%83%89) 新月や朔に関する質問
- [新月の開発](https://bbs.shingetsu.info/thread.cgi/%e6%96%b0%e6%9c%88%e3%81%ae%e9%96%8b%e7%99%ba) この文書への質問や意見
