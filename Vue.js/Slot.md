## スロットとは

- コンポーネントの特定の場所にコンテンツを差し込むことができるようになる

<例>NavigationLinkコンポーネントを使った例
```html
<NavigationsLink url="/profile">
  Your Profile
</NavigationsLink>
```

`NavigationLink`コンポーネントのテンプレートは以下のようになっている

```html
<a :href="url">
  <slot></slot>
</a>
```
コンポーネントを表示するとき、`<slot></slot>`は「Your Profile」に書き換えられる

**スロットには呼び出し時に指定したコンテンツを差し込むことができる**

スロットには`name`属性を使って名前をつけることができる

<例>`BaseLayout`コンポーネント
```html
<div>
  <header>
    <slot name="header"></slot>
  </header>
  <main>
    <slot></slot>
  </main>
  <footer>
    <slot name="footer"></slot>
  </footer>
</div>
```

それぞれのスロットにはコンテンツを差し込むには`<template>`に対して`<v-slot>`ディレクティブにスロット名を指定する

```html
<BaseLayout>
  <template v-slot:header>
    <h1>ヘッダー</h1>
  </template>
  
  <p>メイン</p>
  
  <template v-slot:footer>
    <p>フッター</p>
  </template>
</BaseLayout>
```

こうすることで、指定したスロットにコンテンツを差し込むことができる  
スロット名を指定していないコンテンツは、スロット名を指定していない`<slot></slot>`に差し込まれる
