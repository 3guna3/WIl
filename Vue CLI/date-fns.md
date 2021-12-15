## date-fnsとは

- Date型の処理を簡単に行うことができるライブラリ
- `npm install date-fns`でインストールできる
- 日付を文字列に変換したりできる


### isWithinIntervalメソッド

「日付に当てはまる」といったような判定をする時に使う

例えば次の例では結果はtrueになる
```js
isWithinInterval(
  new Date(2021, 1, 3),
  { start: new Date(2021, 1, 2), end: new Date(2021, 1, 10)
)
```
次の例ではfalseになる
```js
isWithinInterval(
  new Date(2021, 1, 11)
  { start: new Date(2021, 1, 2), end: new Date(2021, 1, 10)
)
```

日付の計算は自分で実装するとやや面倒であるが、こういった便利なライブラリを利用することですっきり書くことができる
