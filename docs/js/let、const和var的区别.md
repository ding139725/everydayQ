### let、const和var的区别

1. 块级作用域
let、const是存在块级作用域的，var不存在块级作用域
2. 变量提升
使用var创建的变量存在变量提升行为，使用let、const创建的变量则不存在变量提升问题。
```js
console.log(a); // undefined
var a = 2;
```
```js
console.log(a);
let a = 2;//报错
```
3. 重复命名
使用var声明的变量可重复命名，let、const声明的变量不可以哦！
```js
var a = 2;
var a = 3;
//可执行
```
```js
let a = 2;
let a = 3; //报错
```
4. let和const区别
let声明的变量可修改指针指向，通常用来声明可变数据。
const声明的变量不可以修改指针指向，通用声明常量。
5. 全局变量问题
使用var创建的变量为全局变量，会将该变量添加为全局属性，例子如下。
```js
var a = 2;
console.log(window.a);//2
let b = 3;
console.log(window.b);//undefined
```
6. 初始值
使用let、var声明变量，可以不给初始值。但是使用const创建变量就必须给初始值！！

* 小知识（初学者注意）
上面说到const声明的不可以修改指针指向，但下面的操作是可以的哦。
```js
const stu = {
    age: 15,
    name: 'key'
};
stu.age = 20; //√
```
但是这样是不行的哦
```js
const stu = {
    age: 15,
    name: 'key'
};
stu = { //×
    age: 16,
    name: 'xiaokey'
}
```