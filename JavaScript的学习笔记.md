# JavaScript的学习笔记

一、JavaScript数据类型

（一）字符串（String）

- 用单引号或双引号括起来表示文本内容，如："Hello" 或 'JavaScript is fun'。
- 可进行拼接等操作，如："Hello" + " World" 得到 "Hello World"。

（二）数字（Number）

- 包括整数和小数，能用于各种数学运算，像加法、减法等。
- 示例：10 + 5得到15，3.14 * 2得到6.28。

（三）布尔（Boolean）

- 仅有true（真）和false（假）两个值。
- 用于条件判断，如if语句中判断条件是否成立。

（四）Null

- 专门表示空值，明确指示此处没有值的情况。

（四）Undefined

- 当变量声明但未赋值时就是此类型，意味着值未确定。

（五）对象（Object）

- 复杂数据类型，可包含多个属性和方法。
- 例如：

``` javascript
let person = {
    name: "John",
    age: 25,
    sayHello: function() {
        console.log("Hello!");
    }
};
```


这里person就是对象，有name、age属性和sayHello方法。

（六）数组（Array）

- 存储一组有序数据，可含不同类型数据。
- 通过索引（从0开始）访问元素，如：

```javascript
let fruits = [ "apple", "banana", "cherry" ];
console.log(fruits[0]); //输出apple
```

二、JavaScript基本语法

1. 变量声明

- var：是较旧的方式。例如： var num = 10; 。变量可以在声明后重新赋值，并且会被提升（变量声明会被提升到作用域的顶部），不过这种提升可能会导致一些不易察觉的错误。
- let：在块级作用域内有效，不会被提升。如在 if 语句或者 for 循环等代码块中声明的 let 变量，只能在该块内访问。例如：

```javascript
if (true) {
    let x = 5;
    console.log(x); 
}
// 在这个花括号外面无法访问x
```




- const：用于声明常量，一旦赋值就不能重新赋值，也有块级作用域。例如：` const PI = 3.14159; `

2. 数据类型

- JavaScript是一种弱类型语言，这意味着在声明变量时不需要指定数据类型。变量的数据类型由它所赋的值决定。例如： let variable;  （此时 variable 是 undefined 类型）， variable = 10; （现在 variable 是 Number 类型）。

3. 运算符

- 算术运算符：和数学中的类似，包括加（ + ）、减（ - ）、乘（ * ）、除（ / ）、取模（ % ）。例如： 1 + 2 等于 3 ， 7 % 3 等于 1 。
- 赋值运算符：除了基本的 = ，还有复合赋值运算符，如` += 、 -= 、 *= 、 /=` 等。例如： `let x = 5;` `x += 3; `等同于` x = x + 3 `，此时 x 的值为 8 。
- 比较运算符：用于比较两个值，返回布尔值。如等于`（ == ）`、全等于`（ = = = ）`、大于`（ > ）`、小于`（ < ）`等。需要注意的是 `==` 会进行类型转换再比较，` = = = `则是值和类型都要相同才返回 true 。例如：` 5 == "5"` 是 true ，` 5 === "5"` 是 false 。
- 逻辑运算符：包括与（ && ）、或（ || ）、非（ ! ）。用于组合或反转布尔值。例如： true && false 是 false ， true || false 是 true ， !(true) 是 false 。

4. 语句

- 条件语句：
- if...else：用于根据条件执行不同的代码块。例如：

```javascript
let age = 18;
if (age >= 18) {
    console.log("You are an adult.");
} else {
    console.log("You are a minor.");
}
```


- switch：用于多分支条件判断。例如：

```javascript
let day = 3;
switch (day) {
    case 1:
        console.log("Monday");
        break;
    case 2:
        console.log("Tuesday");
        break;
    case 3:
        console.log("Wednesday");
        break;
    default:
        console.log("Other day");
}
```


- 循环语句：
- for循环：通常用于已知循环次数的情况。例如，计算1到10的和：

```javascript
let sum = 0;
for (let i = 1; i <= 10; i++) {
    sum += i;
}
console.log (sum);
```


- while循环：在条件为真时重复执行代码块。例如：

```javascript
let n = 0;
while (n < 5) {
    console.log(n);
    n++;
}
```


- do...while循环：和 while 循环类似，但会先执行一次代码块，再判断条件。例如：

```javascript
let count = 0;
do {
    console.log(count);
    count++;
} while (count < 3);
```


5. 函数

- 函数是一组可重复使用的代码块。可以使用 function 关键字来定义函数。例如：

```javascript
function add(num1, num2) {
    return num1 + num2;
}
let result = add(3, 5);
console.log(result); 
```


也可以使用箭头函数，这是一种更简洁的定义函数的方式。例如：` let multiply = (a, b) => a * b;`。
