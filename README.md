#Media Queries Mixi

Sassのメディアクエリー用のmixinです。

##使用方法

使用法は簡単で、「@import」を仕様してファイルを読み込みます。

**style.scss**

```css
@import "./config";
@import "./MediaQueries";

a {
  color: black;
}

@include media (pc) {
  a {
    color: blue;
  }
};

@include media (sp) {
  a {
    color: red;
  }
};
```

「config」ファイルでMedia Queriesの設定をします。
基本となる「$break-points」という変数名は変えないでください。
以下のように連想配列にで書きます。
多次元配列で２次元配列になる時は「min」と「max」としてください。
1次元目は任意で数も複数対応可能です。

**_config.scss**

```css
/* 例１ */
$break-points: (
  pc: 1024px,
  sp: (
    min: 320px,
    max: 640px
  )
);

/* 例2 */
$break-points: (
  max: 1024px,
  mid: 800px;
  min: (
    min: 320px,
    max: 640px
  )
);

```

是非試しに使用してみてください。
