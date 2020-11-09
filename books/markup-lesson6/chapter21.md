---
title: "justify-content"
---

`justify-content` は、Flexboxにも存在したプロパティでしたね。

役割に関しては、Flexboxの `justify-content` も、役割としては「水平方向の位置を指定するプロパティ」ですので、制御する軸の方向に関しては変わりありません。

そのため、用意されている値も、Flexboxのものと、大きくは違いがないのが特徴です。

ただし、用意されている値の名前が、Flexboxとは一部違うものがCSSグリッドの `justify-content` にはあり、**グリッドコンテナー内の、グリッドトラックの行(row)の方向の位置を指定するプロパティ** という役割です。

プロパティ名 | 役割
------------ | -------------
 `justify-content`  | グリッドコンテナー内におけるグリッドトラックの横方向（インライン軸）の位置を指定するプロパティ

コンテナー用のプロパティに用いた例を、CSSグリッドの `justify-content` に書き直してみます。

## justify-content: start;

![](https://storage.googleapis.com/zenn-user-upload/vk2udwcg8izs2omabewfcfldba58)

:::message
以下のソースコードは、下記のリンクから、ダウンロードすることができます。
「lesson6-grid-justify-content」のフォルダが、このチャプター該当ソースコードです。
:::

> [ソースコード](https://github.com/schabibi1/zenn-book-challenges/tree/main/lesson6-grid-justify-content)

```css
/* 他割愛 */

.container-body {
  /* コンテナーに対する、CSSグリッドのスタイル */
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: 1fr 1fr;
  grid-row-gap: 1em;
  justify-content: start;/* 👈 */

  /* その他省略 */
}

/* アイテムに対する、CSSグリッドのスタイル */
/* 省略 */
```

## justify-content: end;

![](https://storage.googleapis.com/zenn-user-upload/ywga1kh07zn1ejtu9rn8ghbv8da4)

```css
/* 他割愛 */
justify-content: end;
```

## justify-content: center;

![](https://storage.googleapis.com/zenn-user-upload/pdug0oixb5fj9sbe4h7im42ayxtu)

```css
/* 他割愛 */
justify-content: center;
```

## justify-content: stretch;

![](https://storage.googleapis.com/zenn-user-upload/pgm8o5v1pyurkf5ui1w7a3erq9x3)

```css
/* 他割愛 */
justify-content: stretch;
```

## justify-content: space-between;

![](https://storage.googleapis.com/zenn-user-upload/o5qyvlyn8cng8e72gj0sw6yn4i68)

```css
/* 他割愛 */
justify-content: space-between;
```

## justify-content: space-around;

![](https://storage.googleapis.com/zenn-user-upload/lzk5y0ht5sso1fall37nrw20zp1f)

```css
/* 他割愛 */
justify-content: space-around;
```

## justify-content: space-evenly;

![](https://storage.googleapis.com/zenn-user-upload/y1khdgwkf1kaw2rj8choj5hy7aoo)

```css
/* 他割愛 */
justify-content: space-evenly;
```

# 値一覧

使用できる値 | 役割
------------ | -------------
 `start` | 左寄せ
 `end` | 右寄せ
 `center` | 中央寄せ
 `stretch` | 軸の領域いっぱいにグリッドトラックを広げる
 `space-between` | 均等に配置(左右の余白なし)
 `space-around` | 均等に配置(左右の余白あり)
 `space-evenly` | 均等に配置(左右の余白もアイテム幅も均等)

# 注意

1つだけ、 `justify-content` プロパティを付与するときに、気をつけたいことがあります。

それは、 **`justify-content` プロパティが無効になる場合がある** ことです。

例えば、先ほどの例では、 `grid-template-columns: auto;` としていて、 `1fr` で等分に分割をしていないのに気が付いたでしょうか？

これを、今までのプロパティのチャプター同様に

```css
grid-template-columns: 1fr 1fr;
```

と、戻してみるとどうなるでしょうか？

右寄せになる `end` を値に指定して、 `justify-content` を付与します。

![](https://storage.googleapis.com/zenn-user-upload/gu5gd7to2ayypfg19d479ie73huf)

グリッドアイテムは、右寄せにはならず、左寄せのままですね。

そのほかの値を付与しても、無効になってしまいます。

これは、 `justify-content` が、 **コンテーナー内に、ある程度の要素が伸び縮みできる余白がない場合は、無効になってしまう** という特性があるからです。

Flexboxに、マークアップ言語シリーズの本には取り扱いがありませんでしたが、マイナーなプロパティで `flex-grow` というものがあります。

これは、CSSグリッドの `grid-template-rows` や `grid-template-colums` と非常に似ているもので、 `fr` という単位はありませんが、 `flex-grow: 1;` などのようにして、アイテムの伸縮を行うことができるというものです。

アイテムを伸ばしたり、縮めたりするのには、それなりの余白スペースが必要になるので、 `grid-template-columns` や `grid-template-rows` でアイテムと余白をどのくらいの大きさで、均等に分割するのかを決めてしまっている状態では、余白がコンテナーに存在しないので、無効化されるということなんです。

要するに、 **グリッドトラックがある範囲は、アイテムが存在しなくても余白ではない** ので、 **余白を使って伸び縮みをする `justify-content` の、伸縮スペースがない状態** ということです。