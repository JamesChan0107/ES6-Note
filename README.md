箭頭函數
1.基本語法：
Const/let function的名稱 (參數1,參數2,參數3,……) => { statement;}
2.注意事項：
如果參數只有一個的話，就可以省略小括號
如果statement code只有一段的話，可以省略大括號，並且會直接做return
如果沒有參數or參數>=2個，就需要加上小括號
關於var、let 與 const
1.Var：
作用區域是”Function Scope”，指的是在一個function內部宣告var，這個變數只會在function內部可以看到。
(例: var globle = "全域變數"
function a() {
    var local = "區域變數"
    console.log(local)
}
a() //區域變數
console.log(globle) //全域變數
console.log(local) // Uncaught ReferenceError: local is not defined)
若在if或for迴圈內宣告var，這個被宣告的變數會變成”全域變數”，這是因為var非Block Scope。
(例: if(true){
    var a = "我會跑到全域"
}
console.log(a) //印出“我會跑到全域”)
Var可以重複宣告，這可能會導致變得難以維護
(例: var a = "apple"
var a = "banana"
console.log(a) // 印出banana)
2.let：
作用區域是”Block Scope”，有了這個特性，即使在( if 或 for…loop )裡面宣告變數，也不會自動轉為全域變數。
Let不像var一樣可以重複宣告，但它可以重新賦值，簡單來說我如果已經宣告一個let a=10，我就不能再宣告例如let a=11，這樣console.log(a)會印不出東西，但如果我下一行在打一個a=11，就能成功將a的值改為11。
3.const：
const比let更加嚴謹，const可以看成constant 常數，有不變的意思，跟let一樣都是屬於Block Scope、不可以重複宣告。
const 不可以重新賦值，因為const是不變的常數，因此重新賦值的話，可能會出現錯誤，例如我宣告const a =10，又多打一個a = 11，console.log(a)可能會出現TypeError。

模板字串
以前都需要用一堆的+來把變數和字串用在一起，例如var str = 'example line: ' + line1 + '\n' + 'column: ' + column;，然而透過``就能框住一串的文字、變數、符號等等，並且可以使用${變數名稱} 直接將變數放在整個字串的自訂位置。最後，模板字串支援換行符號，我們不再需要使用 \n 表示換行。

解構賦值
可以把陣列或物件中的資料解開擷取成為獨立變數
(例:const foo = ["Leo", "John", "Mary"];
const [one, two, three] = foo;
console.log(one); // "Leo"
console.log(two); // "John"
console.log(three); // "Mary")


展開運算子
只要多加…，就可以將加入的例如說數組給展開來，並進行後續操作
(例: 原先：
function add(a, b, c) {
 return a + b + c
}
console.log(add(1, 2, 3))
// 6
ES6:
function add(a, b, c) {
 return a + b + c
}
var arr = [1, 2, 3]
console.log(add(…arr)) // ...arr 等於展開 arr 就會變成如上述所示
// 6)



(後續實作上有學到更多會在加進來筆記內~)
參考來源：
1.	https://hugh-program-learning-diary-js.medium.com/javascript-%E9%80%B2%E9%9A%8E-es6-3a65102157e6
2.	https://medium.com/@theallisonlai/var-let-const-%E7%9A%84%E5%B7%AE%E5%88%A5-95ddc0f3a3d8
3.	https://medium.com/%E4%B8%80%E5%80%8B%E5%B0%8F%E5%B0%8F%E5%B7%A5%E7%A8%8B%E5%B8%AB%E7%9A%84%E9%9A%A8%E6%89%8B%E7%AD%86%E8%A8%98/javascript-es6-%E6%A8%A1%E6%9D%BF%E5%AD%97%E4%B8%B2-template-string-%E7%9F%A5%E5%A4%9A%E5%B0%91-7f2b1d67812e
