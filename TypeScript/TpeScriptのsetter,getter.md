## TypeScriptのsetterとgetter

<例>

```ts
class Book {
 
 // privateなので、setterやgetterを使わないとアクセスできない
 private _name: string = '';
 
 // セッターを定義、型は合わせること
 set name(value: string) {
   if (value === '') {
      console.log('書式名が指定されていません')
   } else {
      this._name = value;
   }
  }
  
  get name(): string {
    return this._name;
  }
}

let mybook: Book = new Book();
mybook.name = 'JavaScript入門';
console.log(mybook.name)
```

上記内容をトランスコンパイルを実施するとエラーが発生する
```
tsc ファイル名.ts

// error
Accessors are only available when targeting ECMAScript 5 and higher.
```
セッターはES5以降でないと使用できないというエラーが発生  
通常`tsc`というコマンドでトランスコンパイルを実施しようとするとES5以前で実施される

セッターなどはES5以降でないと使用できないので、以下のようにトランスコンパイルを行う！

```
tsc -t ES5 ファイル名.ts
```

上記コマンドで正常にコンパイルができる！
