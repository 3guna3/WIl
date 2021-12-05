## TypeScriptのクラス定義

型を明示してクラスを作成していく

<例>

```ts
class Item {
  // publicはクラス外でも変更可能
  public tax: number
  // privateはクラスの中からしか変更ができない
  private price: number
  
  // ?というのは省略可能なパラメーター、そのため省略されるとundefinedが入る
  constructor(price: number, tax?: number) {
    if (tax) {
      this.tax = tax;
    } else {
       this.tax = 10;
    };
    
    if (isFinit(price)) {
       this.price = price;
    } else {
       this.price = 0
    };
   };
   
   // ファンクションに関しても明示
   public getTax (): number {
     return Math.round(this.price * (this.tax / 100));
   }
 };
 
 let apple: Item = new Item(180);
 console.log(apple.tax);
 console.log(apple.getTax());
```
