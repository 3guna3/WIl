## props

Vueでは複数のコンポーネントを組み合わせて1つのページを作成する。  
コンポーネントには親とこの関係があり、全体としてツリー状に構築される。

親コンポーネントの値を子のコンポーネントに渡したいときは、`props`を使う。  

**<例>**

src/components/Hoge.vue
```vue
<template>
  <div>
    <p>{{ message }}</p>
  </div>
</template>

<script>
  export default {
    name: "HelloWorld",
    
    // 親コンポーネントからmessageを受け取る
    props: ['message'],
  };
</script>
```

`props`にmessageを指定することで、親コンポーネントからその値を受け取ることができる。

**親コンポーネント**

/src/App.vue
```vue
<template>
  <div id="app">
    <!--messageの値を渡す-->
    <HelloWorld message="Hello World!" />
  </div>
</template>
```
