---
title: "Composition APIの簡易的な使い方"
free: true
---

# Composition APIを使って、カウンターアプリを実装しよう！

では、いよいよカウンターアプリを実装していきます。

機能設計と、画面、遷移設計（ワイヤーフレーム）をチャプター3で作成していますので、そちらを以下で再度ざっと見直しながら取り組んでみましょう

### 機能設計（機能仕様）

| アプリ概要 | 必要な機能(機能設計) |
| ---- | ---- |
| 数値カウントアプリ | クリックイベントが発生するたび、1ずつ数値が加算されて増える |

この機能要件を満たすアプリをComposition APIで作成してみましょう

# 開発環境のセットアップ

まずは `Vue CLI` を使用し、開発環境を整えます。

> Vue CLI公式ドキュメント: [「Vue CLI」](https://cli.vuejs.org/)

## Vue CLIのインストール

まだVue CLIをインストールしていない方は事前にインストールをしておきましょう

パッケージ管理にnpmを使用されている場合には以下のコマンドを実行してください

```shell
npm install -g @vue/cli
```

パッケージ管理にyarnを使用されている方は以下のコマンドを実行しましょう

```shell
yarn global add @vue/cli
```

:::message
Nodeバージョンは、v8.9以上の環境が必要です。
バージョンがこれより低い場合は、推奨版をNode公式ドキュメントで確認し、Nodeバージョン管理ツール（nなど）でアップグレードをしましょう。
:::

![](https://storage.googleapis.com/zenn-user-upload/4r8zs019fjh7wm90os61y9rw5uo8)

> [Node公式ドキュメント、インストール](https://nodejs.org/en/)

> [Node バージョンマネージャー、n](https://github.com/tj/n)

:::message
本教材では、以下のNodeバージョンとyarnバージョンです。
:::

```js
{
  node: "14.17.0",
  yarn: "6.14.13"
}
```

 `Vue CLI` を使って開発環境が整えましょう
 
```shell
vue create composition-counter-app
```

アプリを作成しようとするとVueのバージョンを選択することになります。必ず「Vue3」を選択してください

```shell
Vue CLI v4.5.13
? Please pick a preset: (Use arrow keys)
  Default ([Vue 2] babel, eslint) 
❯ Default (Vue 3) ([Vue 3] babel, eslint) 
  Manually select features
```
`Vue CLI` を使って開発環境が整ったら、プロジェクトをローカル環境で立ち上げましょう。

```shell
yarn serve
```

![](https://storage.googleapis.com/zenn-user-upload/5ca349a8e54c0386e3031050.png)

上記の画面が表示され、立ち上がったら、プロジェクトディレクトリの `src/App.vue` ファイルを開きます。

以下のデフォルトソースコードの記述があることを確認します。

```vue:src/App.vue
<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

カウンターアプリを開発するため、不要な記述は以下のように削除、もしくは編集します。

```diff jsx:src/App.vue
<template>
-  <img alt="Vue logo" src="./assets/logo.png">
-  <HelloWorld msg="Welcome to Your Vue.js App"/>
+  <div className="app">
+    HEY👋
+  </div>
</template>

<script>
- import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
-  components: {
-    HelloWorld
-  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

仮に入れた「HEY👋」という文字列がアウトプットされていることが確認できるかと思います。

![](https://storage.googleapis.com/zenn-user-upload/b98ddeab1c319ac4e55ac151.png)

# Composition APIの読み込み

では、Composition APIでリアクティブなStateを扱うために、 `ref` をインポートしましょう

そしてrefを使ってcountというstateを用意します

カウントを0から始めたいので、refの引数には、0を格納します。

またstateをテンプレートから読み込みたいので、テンプレート上で扱うstateに関してはsetupで値を返すようにします

```diff vue:src/App.vue
<script>
+ import { ref } from 'vue'

export default {
  name: 'App',
+  setup() {
+   const count = ref(0)
+
+    return {
+      count
+    }
+  }
}
</script>
```

クリックイベントによって、数値の加算を1ずつ行いたいので、ボタン要素をtemplate内に用意します。

クリックイベントの結果、要するに1ずつ加算された結果をブラウザに表示したいので、文字列で出力させる記述も書き加えます。

```diff vue:src/App.vue
<template>
  <div className="app">
+    <h1>Counter App 🧮</h1>
+    <button>+</button>
+    <h3>{{count}} times clicked!🖱</h3>
  </div>
</template>
```

この時点でブラウザの反映を確認してみると、stateのcount初期値0が、既に返り値として返されていることが確認できます。

![](https://storage.googleapis.com/zenn-user-upload/vzx3bi16k3vdbf3hx4gzzvlr5faz)

# クリックイベントによってstateを変更する

今の状態だと、ボタン要素をクリックしてもクリックイベントの反応がないので、イベントによってstateが変更されるようにします

まずは、クリックイベント発生時に、イベントがトリガーされているかどうかの検証を行います。

:::message
**検証のコツ:**
構造がシンプルなうちにイベントがトリガーされているかを検証すると、構造が複雑化する前に、イベントトリガーにエラーの原因が潜んでいないことが断言できます。要因を絞り込みやすくするコツです。
:::

```diff vue:src/App.vue
<template>
  <div className="app">
    <h1>Counter App 🧮</h1>
-     <button>+</button>
+    <button @click='increment'>+</button>
    <h3>{{count}} times clicked!🖱</h3>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'App',
  setup() {
    const count = ref(0)

+   const increment = () => {
+     console.log('fired!')
+   }

    return {
      count,
+     increment
    }
  }
}
</script>
```

![](https://storage.googleapis.com/zenn-user-upload/24274c75c1446c2aaec57ba5.png)

ブラウザdev toolのコンソールに、クリックした回数だけイベントが発生して、「fired!」の文字列が出力されていることが確認できますね。

では、1ずつstateのcountに、加算をしていく記述をしていきたいと思います。

チャプター4のrefの基本構文を確認しながら書いていきましょう。

```diff vue:src/App.vue
<template>
  <div className="app">
    <h1>Counter App 🧮</h1>
    <button @click='increment'>+</button>
    <h3>{{count}} times clicked!🖱</h3>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'App',
  setup() {
    const count = ref(0)

    const increment = () => {
      count.value++ // 「count.value = count.value + 1」と同意
    }

    return {
      count,
      increment
    }
  }
}
</script>
```

![](https://storage.googleapis.com/zenn-user-upload/rrsveqqxo9m8pp3p2m5400pss6d1)

クリックイベントが発生した回数分、1ずつstateのcountが加算されていることが確認できます。

カウンターアプリが、とても簡単にできましたね。