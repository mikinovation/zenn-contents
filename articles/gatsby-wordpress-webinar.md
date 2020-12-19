---
title: "Gatsby公式Webinarまとめ: Gatsby.jsとWordPressのHeadless CMSのススメ"
emoji: "🧙‍♂️"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["javascript", "react", "gatsby", "wordpress", "headlesscms"]
published: true
---

どうもー、ドイツでフリーランスのフルスタックエンジニアをしています、Arisaです。

教材販売と、個別プログラミング学習サポートを提供する、[「オーダーメイド感覚プログラミング学習サービス | Lilac（ライレック）」](https://note.com/frontendlifeinde/m/m9b8feda1d547)を開発しています。

3年間、40名以上マンツーマンで教え、国内、海外の企業にweb系エンジニアとして就職した卒業生や、フリーランスのエンジニアとして成功した卒業生もいます。

[Lilac](https://note.com/frontendlifeinde/m/m9b8feda1d547)では公式ドキュメントや上級者向けのチュートリアルではわかりにくい内容も、読むだけでわかる教材と、実践に備えたサポートを大切にしています。

# この記事を書くに至った経緯

## Code Polaris アドベントカレンダーのエントリー

さて、今回のこの記事は、ちょっと過ぎてしまいましたが...[Code Polaris アドベントカレンダー](https://qiita.com/advent-calendar/2020/code-polaris)18日目のエントリーです🌌

[Code Polaris](https://code-polaris.connpass.com/)とは、女性による女性のための技術コミュニティです。

今のところは女性限定のコミュニティですが、日々、女性技術者同士がわいわい集まって、楽しく技術トークや悩みを含む雑談をしたり、オンライン勉強会イベントをしたり、OSS開発の話を進めたりと、私もとても楽しく参加させていただいています。

私が配信しているPodcast、[「アノニマスですけど何か」](https://note.com/frontendlifeinde/m/m14ff18669c56)でも紹介させていただきました。

> [[技術イベント] オンラインコミュニティとイベントが今アツい](https://note.com/frontendlifeinde/n/n6742f5cb3aa5?magazine_key=m14ff18669c56)

## Gatsby.jsの公式Webinarを推したい

[Gatsby.js](https://www.gatsbyjs.com/)推しなので、最近参加した公式Webinarのまとめを日本語でして、良さをもっと推したいので書きました。

最近ようやく日本語ソースや技術書も増えてきたなと思います。

でも、[Gatsby.jsさんのWebinar](https://www.gatsbyjs.com/resources/webinars/)については、無料で良質、かつホットなトピックも取り扱われているのに、コメントなどを観察していると、見てる人が少ない気がしました。

Quick Start系のチュートリアルは、もう情報が溢れているので、こういう面白いオンラインイベントがあるよという情報の方が、最近は自分としても興味があるので、参加した回のWebinarの推しどころを書こうと思います。

# この記事の対象者

- Gatsby.jsをある程度書いたことがあるエンジニア。
- Headless CMSのメリットに興味があるエンジニア。
- Gatsby.js x WordPress、Gatsby.js x ECサイトの実例を見たい人。

# 今回のwebinarスピーカー

- Robin Zimmerさん (Full-stack Web Developer, Jambaree)
- Blaine Yamakawaさん (Project Manager and UX Designer, Jambaree)
- Jason Bahlさん (Software Engineer, Gatsby)

の3人でした。

[Jambaree](https://jambaree.com/about-us)という、 [Bare Advertising & Communications](https://bare.ca/)の子会社で、バンクーバーベースの広告会社だそう。

GatsbyとJAMstack主軸のエンジニアが勢揃いした、

- Gatsby.js x WordPress
- Gatsby.js x ECサイト

の、組み合わせを強みにしているチームだそうです。

> 今回の回のwebinar **「WordPress Without the Worry: Going Headless with Gatsby」** : [https://www.gatsbyjs.com/headless-wordpress-webinar](https://www.gatsbyjs.com/headless-wordpress-webinar)

# 参加したGatsby.js 公式webinarのトークコンテンツ

前半は、[Jambaree](https://jambaree.com/about-us)の中の人が、Gatsby.js x WordPressの組み合わせ最高だよと実例を元に、具体的に何が良いのかを見せてくれる内容と、スピードが4倍爆速化した種明かしと、Before、Afterでセキュリティなどの問題がどう向上したのかというwebinarでした。

## Jambareeのプレゼンコンテンツ

1. About Jambaree
2. [RealCedar.com](https://www.realcedar.com/)
3. Previeous WordPress website
4. Going Headless with Gatsby
5. The Result

後半は、Gatsby.jsのソフトウェアエンジニアの方が、興味を持った人向けに、こんなに簡単にGatsby.js x WordPressの導入はできますよ、というdemoのプレゼンですね。

## Gatsby.jsのプレゼンコンテンツ

1. WHAT is Gatsby.js x WordPress?
2. WHY Gatsby.js x WordPress?（Speed, Security, Modern Tooling, Decouple Concerns）
3. WHO is this for?（Content Creators, Developers, End Users）
4. WHERE to use?（Cloud, Gatsby Cloud）
5. **HOW to start?（これがメイン）**

# Jambareeプレゼンのまとめ

Jambareeのプロジェクトを元に、実例ベースで

- WordPressもECも、Gatsby.jsだとセキュリティの脆弱性も克服できること
- ヘビーなコンテンツのサイトボリュームでも、パフォーマンスの軽さを維持できること

などをプレゼンするのが基本でした。

それぞれの実例を見せながら、そもそもなぜGatsby x WordPress と Gatsby.js x ECサイト推しなのかを解説していました。

数年前に、WordPressをHeadless化することが流行りましたが、当時流行したときは、まだGatsby.jsはv1とかで、あまり騒がれていなかったので、WordPressのHeadless化の主流ツールではなかったように記憶しています。

当時の私は、WordPressのデメリットにフォーカスをしてしまい、嫌気がさして遠ざかっていました。

が、そんな私にとっても、このwebinarは、WordPressのセキュリティ脆弱性や、SEOがいまいちパッとしない問題や、プラグインによるサイトのもったり感を解決し、WordPressをCMSとして見直す機会になったと思っています。

マルチ言語サイトでも、軽やかにHeadlessの構造を維持したまま、WPのプラグインに頼らずに、スリムなサイトの構築ができることも推していました。

アーカイブを見る時間がない方のために、簡単な図で、Gatsby.js x WordPressの構造を見せてくれたのを元にすると、こんな感じです。

![](https://storage.googleapis.com/zenn-user-upload/ye4rkqf31kn3s1h309rmrbd8ta5n)

Gatsby.jsでデータクエリを構成するGraphQLは、WordPressプラグインで導入で、あとはGatsby.jsに馴染みのある人であれば、クエリはGatsby.jsの公式ドキュメントにあるように組んでいけばOKです。

Gatsby.jsは、画像の多いサイトにもとても適しているので、そこも主張していました。

今回のJambareeのモデルの構造的には、このようになっているものが多いようです。

- WordPress自体はCloudinaryと紐づけておいて、そこに画像を管理
- NetlifyなどのホスティングサービスにGatsby.jsをビルドするよう紐付け

従来の画像軽量化WordPressプラグイン（一定以上の容量は有料）を導入することなく、画像の量に左右されず、サクサク動くサイトを実現できるというわけです。

しかもこれでマルチ言語対応していて、スピードも落ちないので、すごい。

[RealCedar.com](https://www.realcedar.com/)を実際に開いてみると、サクサクです。

フォームやサーチ機能へのアプローチも紹介していたけど、こちらはとてもあっさりだったので割愛。

## 改善点

ビルドにかかる時間に関しては、キャッシュが少し苦戦したようで、若干Gatsby.jsへのリクエスト的な感じで語っています。

gatsby-plugin-netlify-cacheのGatsby製プラグインを導入していたけれども、Gatsby側のアップデートに伴って、netlify-plugin-gatsby-cacheに移行する手間がちょっとあったようです。

どんな便利なフレームワークやライブラリでも欠点はあります。

大幅アップデートの際には、今まで使っていたプラグインが動かなくなって、使うプラグインそのものを見直し/変更する手間が発生する場合もあるのは、Gatsby.jsの少ないデメリットの1つですね。

主要な公式プラグインを使うとある程度は軽減されますが、このような手間とリスクは、ないに越したことはないです。

そんなに規模が大きくないプロジェクトでも、ビルドにかかる時間が少し長いことも、Gatsby.jsの、もう1つの数少ないデメリットなので、そこも少し改善されれば、もっとファンは増えるはず、とも思っています。

画像に関して、Gatsby.jsのパフォーマンスは素晴らしいと絶賛してましたが、WordPressの持つ構造とのすり合わせが必要だった部分は若干あったようです。

WordPressでの画像サイズは問題だったらしく、WordPressのv5.3以降は、不必要なリサイズ画像がたくさんできてしまうという不便な面があったようで、アップロード後に画像リサイズをしなければいけなかったのは、まあ面倒だったけど解決したよと、最後に正直に言ってました。

どんな技術でもメリットとデメリット両方がありますから、そこは、今後の改善に期待です。

## Gatsby.js x WordPress / Gatsby.js x ECサイトのパフォーマンスの結果

実際、この実例で使われていたプロジェクトでは、

- Organic Trafic: +66%
- Conversion: +35%
- Download: +186%

という良い数値を叩き出したそうです。

やはりレスポンスが早いサイトは、ユーザーにとって好印象のようですね。

# Gatsby.jsプレゼンのまとめ

ものすごく極端に一言でまとめると、5W1HでGatsby.jsとWordPressの開発について、メリットとクイックスタートにフォーカスして話があった感じです。

導入方法がいかに手軽かを見せる前にも、なぜGatsby.js x WordPressを採用する理由についてはメリットがはっきりしていました。

## メリット

- デフォルトでどんなスケールのプロジェクトでも早いスピード
- ライブサーバーのセキュリティ問題の解決
- ReactやTypeScriptなど、モダンな技術スタック
- WordPressとフロントエンドを切り分けられるので、ホワイトアウトになるリスクがない

導入方法は、実際にスターターを使った簡単なdemoをしてくれました。

## 導入方法

1. WordPressプラグインのインストール（[WPGraphQL](https://www.wpgraphql.com/)と、[WPGatsby](https://www.wpgraphql.com/extenstion-plugins/wpgatsby/)）
2. Gatsbyが提供しているWordPressスターターを使ってGatsby.jsでサイトを構築
3. GraphQLとビルドコンポーネントを使う
4. [Gatsby Cloud](https://www.gatsbyjs.com/)にデプロイ

本当にこの4ステップだけで終わっちゃいます。

上記の4ステップを、実際に収録した動画を見せながら解説してくれました。

[Local](https://localwp.com/)などのローカル環境開発ツールを導入し、プラグインをインストールして、[GatsbyのWordPressスターター](https://github.com/gatsbyjs/gatsby-starter-wordpress-blog)をforkします。

fork後に、 `gatsby-config.js` ファイルにて、以下のurlの値を、environment variableに変更します。

```javascript
plugins: [
    {
      /**
       * First up is the WordPress source plugin that connects Gatsby
       * to your WordPress site.
       *
       * visit the plugin docs to learn more
       * https://github.com/gatsbyjs/gatsby-source-wordpress-experimental/blob/master/README.md
       *
       */
      resolve: `gatsby-source-wordpress-experimental`,
      options: {
        // the only required plugin option for WordPress is the GraphQL url.
        url:
          process.env.WPGRAPHQL_URL ||
          `https://wpgatsbydemo.wpengine.com/graphql`,
      },
    },
```

[Gatsby Cloud](https://www.gatsbyjs.com/)にここまでできたら紐付けします。

![](https://storage.googleapis.com/zenn-user-upload/s5lc9xue9rpc4ilmes1e2yap9h83)

Github/Gitlabリポジトリを紐付けでき、デプロイ先をNetlifyやそのほかホスティング先に指定できます。

WordPressダッシュボードで、[WPGatsbyプラグイン](https://www.wpgraphql.com/extenstion-plugins/wpgatsby/)の設定画面で、web hookを登録します。

これだけでWordPressサイトのプレビューでサイト自体は確認ができ、投稿を反映させることもできます。

GraphQLを使って、データクエリ操作も手軽にできるので、developer firstな体験ができることも、簡単にライブコードで見せてくれました。

# そのほかwebinarのアクティビティ

Gatsbyの公式webinarは、webinarの合間に、2, 3個ほど簡単な参加型のクイズがあったり、webinarの最後には参加者からの質問に答えたりします。

参加者はマイクとカメラオフなので、気軽に参加できます。

質問は、webinar進行中に書き込む感じでした。

# まとめ

Gatsbyのwebinarは、コロナ渦になってから頻度が増えたので、オンラインイベントで英語圏のものはハードル高いなという方でも、自分のタイミングで質問があれば書き込むだけで良いのは、参加のハードルがグッと下がって良いと思いました。

観るだけの参加も十分できるので、忙しい人にも気軽に参加できるという印象です。

字幕はライブ配信の時はないですが、ライブで観るように参加登録だけしておいて、あとでYoutubeのアーカイブ公開リンクが送られてくるので、そこで字幕をつけることで理解することもできます。

何よりも良いのは、Gatsby内のdeveloperや、実践例を無料で観ることができるということですね。

過去のアーカイブも、Gatsby公式サイトのwebinarページより、リクエストのメールを登録するか、こちらの公式Youtubeチャンネルのwebinarsでまとめてあるページから、多分全てのアーカイブが見れます。

> Gatsby.js アーカイブwebinars: [https://www.youtube.com/watch?v=v88snd6EUaY&list=PLCU2qJekvcN3gKu0F2g-EoIKGskszyg-p](https://www.youtube.com/watch?v=v88snd6EUaY&list=PLCU2qJekvcN3gKu0F2g-EoIKGskszyg-p)

良質なwebinarが無料でみることができるGatsby.jsの公式webinar、一度参加してみてはどうでしょうか？💡