## Vuelidateとは
バリデーションを行うライブラリ  

**インストールの仕方**
```sh
npm install vuelidate --save
```
### mixin
Vuelidateライブラリの`validationMixin`というmixinをimportし、`mixin`でそれを指定する

[Vueのmixin](https://jp.vuejs.org/v2/guide/mixins.html)はコンポーネントに任意のmixinオブジェクトを`混ぜる`ことができる機能

<例>
```vue
<script>
// mixinオブジェクトを定義
const myMixin = {
  created() {
    conosole.log('hello')
  }
}

export default {
  mixins: [myMixin], // mixinオブジェクトを混ぜる
  created() {
    console.log('world');
  }
};
</script>
```

出力結果
```
"hello"
"world"
```

mixinオブジェクトで記載したcreatedの処理がコンポーネントに混ぜ込まれて実行される  
`validationMixin`はVuelidateライブラリが提供するmixinオブジェクトなので、これをmixinに指定することでVuelidateの機能が使えるようになる。
