# JavaScript基础知识练习

## 1. 变量的定义

JavaScript中有三种声明变量的方式：

```javascript
var name = "Alice";      // var：函数作用域，可重复声明
let age = 30;           // let：块级作用域，不可重复声明
const PI = 3.14;        // const：块级作用域，声明后不可重新赋值
```

打印变量：

```javascript
console.log("Name:", name);
console.log("Age:", age);
console.log("PI:", PI);
```

---

## 2. 变量的类型

使用 `typeof` 运算符可以查看变量的类型：

```javascript
console.log("Name type:", typeof name);   // string
console.log("Age type:", typeof age);     // number
console.log("PI type:", typeof PI);       // number
```

---

## 3. JavaScript中的数据类型

JavaScript共有7种原始数据类型 + 1种复杂数据类型：

### 原始类型（Primitive Types）

| 类型 | 示例 | 说明 |
|------|------|------|
| **String** | `"Hello"` | 字符串 |
| **Number** | `30`, `3.14` | 数值 |
| **Boolean** | `true`, `false` | 布尔值 |
| **Null** | `null` | 空值（typeof返回object） |
| **Undefined** | `undefined` | 未定义 |
| **BigInt** | `123456789012345678901234567890n` | 大整数 |
| **Symbol** | `Symbol("unique")` | 唯一标识符 |

### 代码示例

```javascript
let isStudent = true;                       // boolean
let score = null;                            // null
let undefinedVar;                            // undefined（未赋值）
let bigIntNum = 123456789012345678901234567890n; // BigInt
let symbolVar = Symbol("unique");           // Symbol

console.log("isStudent type:", typeof isStudent);   // boolean
console.log("score type:", typeof score);           // object（历史bug）
console.log("undefinedVar type:", typeof undefinedVar); // undefined
console.log("bigIntNum type:", typeof bigIntNum);   // bigint
console.log("symbolVar type:", typeof symbolVar);   // symbol
```

---

## 4. 运算符与表达式

### 4.1 算术运算符

```javascript
let a = 10;
let b = 5;

console.log("a + b =", a + b);  // 15  加法
console.log("a - b =", a - b);  // 5   减法
console.log("a * b =", a * b);  // 50  乘法
console.log("a / b =", a / b);  // 2   除法
console.log("a % b =", a % b);  // 0   取模（余数）
```

### 4.2 赋值运算符

```javascript
a += 5;    // 等价于 a = a + 5，结果 a = 15
console.log("a after += 5:", a);

b -= 2;    // 等价于 b = b - 2，结果 b = 3
console.log("b after -= 2:", b);

// 其他赋值运算符：-=、*=、/=、%=
```

### 4.3 逻辑运算符

```javascript
let c = true;
let d = false;

console.log("c && d =", c && d);  // false  与运算（两边都为true才为true）
console.log("c || d =", c || d);  // true   或运算（至少一边为true就为true）
console.log("!c =", !c);          // false  非运算（取反）
```

### 4.4 比较运算符

```javascript
let a = 10;
let b = 5;

console.log("a > b =", a > b);    // true   大于
console.log("a < b =", a < b);    // false  小于
console.log("a >= b =", a >= b);  // true   大于等于
console.log("a <= b =", a <= b);  // false  小于等于
console.log("a == b =", a == b);  // false  等于（值相等，不比较类型）
console.log("a != b =", a != b);  // true   不等于
```

> **注意**：`==` 与 `===` 的区别
> - `==`：松散相等，会进行类型转换后再比较
> - `===`：严格相等，类型和值都必须相同

```javascript
console.log(5 == "5");   // true（字符串转数字）
console.log(5 === "5");  // false（类型不同）
```

---

## 5. 流程控制

### 5.1 if-else 条件判断

```javascript
let score = 85;

if (score >= 90) {
    console.log("Grade: A");
} else if (score >= 80) {
    console.log("Grade: B");
} else if (score >= 70) {
    console.log("Grade: C");
} else if (score >= 60) {
    console.log("Grade: D");
} else {
    console.log("Grade: F");
}
// 输出：Grade: B
```

### 5.2 switch 语句

```javascript
let day = 2;
switch (day) {
    case 1:
        console.log("星期一");
        break;
    case 2:
        console.log("星期二");
        break;
    default:
        console.log("其他");
}
```

---

## 6. 循环控制

### 6.1 for 循环

```javascript
for (let i = 0; i < 5; i++) {
    console.log("For loop iteration:", i);
}
// 输出：0, 1, 2, 3, 4
```

### 6.2 while 循环

```javascript
let j = 0;
while (j < 5) {
    console.log("While loop iteration:", j);
    j++;
}
// 输出：0, 1, 2, 3, 4
```

### 6.3 do-while 循环

```javascript
let k = 0;
do {
    console.log("Do-while iteration:", k);
    k++;
} while (k < 5);
// 至少执行一次
```

### 6.4 for...in 和 for...of

```javascript
let arr = ["a", "b", "c"];

// for...in：遍历对象的键或数组的索引
for (let index in arr) {
    console.log("Index:", index);
}

// for...of：遍历可迭代对象的值
for (let value of arr) {
    console.log("Value:", value);
}
```

---

## 7. 函数定义与调用

### 7.1 函数声明

```javascript
function greet(name) {
    return "Hello, " + name + "!";
}

console.log(greet("Alice")); // 输出：Hello, Alice!
```

### 7.2 函数表达式

```javascript
const add = function(a, b) {
    return a + b;
};

console.log(add(3, 5)); // 输出：8
```

### 7.3 箭头函数（ES6+）

```javascript
const multiply = (a, b) => a * b;

console.log(multiply(3, 5)); // 输出：15
```

### 7.4 函数参数默认值

```javascript
function greet(name = "World") {
    return "Hello, " + name + "!";
}

console.log(greet());        // Hello, World!
console.log(greet("Alice")); // Hello, Alice!
```

---

## 8. 数组（Array）

### 8.1 创建数组

```javascript
let fruits = ["Apple", "Banana", "Orange"];
let numbers = new Array(1, 2, 3, 4, 5);
```

### 8.2 常用数组方法

```javascript
let arr = [1, 2, 3];

arr.push(4);      // 末尾添加：[1, 2, 3, 4]
arr.pop();        // 末尾删除：[1, 2, 3]
arr.unshift(0);   // 头部添加：[0, 1, 2, 3]
arr.shift();      // 头部删除：[1, 2, 3]
arr.length;       // 长度：3
arr.includes(2);   // 是否包含：true
arr.indexOf(2);    // 索引：1
```

### 8.3 数组遍历

```javascript
let nums = [1, 2, 3];

// forEach
nums.forEach((num, index) => {
    console.log(`Index ${index}: ${num}`);
});

// map（返回新数组）
let doubled = nums.map(num => num * 2);
console.log(doubled); // [2, 4, 6]

// filter（返回满足条件的元素）
let evens = nums.filter(num => num % 2 === 0);
console.log(evens); // [2]

// reduce（汇总）
let sum = nums.reduce((acc, num) => acc + num, 0);
console.log(sum); // 6
```

---

## 9. 对象（Object）

### 9.1 创建对象

```javascript
let person = {
    name: "Alice",
    age: 30,
    greet: function() {
        return "Hello, I'm " + this.name;
    }
};
```

### 9.2 访问对象属性

```javascript
console.log(person.name);     // Alice（点号语法）
console.log(person["age"]);   // 30（方括号语法）
```

### 9.3 对象方法

```javascript
console.log(person.greet()); // Hello, I'm Alice
```

### 9.4 解构赋值

```javascript
const { name, age } = person;
console.log(name); // Alice
console.log(age);  // 30
```

---

## 10. 字符串（String）

### 10.1 字符串常用方法

```javascript
let str = "Hello, World!";

str.length;                    // 13
str.toUpperCase();             // "HELLO, WORLD!"
str.toLowerCase();             // "hello, world!"
str.indexOf("World");          // 7
str.slice(0, 5);               // "Hello"
str.replace("World", "JavaScript"); // "Hello, JavaScript!"
str.split(",");                // ["Hello", " World!"]
str.trim();                    // 去除首尾空格
```

### 10.2 模板字符串

```javascript
let name = "Alice";
let age = 30;

let message = `My name is ${name}, I'm ${age} years old.`;
console.log(message);
// My name is Alice, I'm 30 years old.
```

---

## 11. 练习题

### 基础题
1. 声明一个变量 `name`，赋值为你的名字，并用 `console.log` 打印
2. 计算 `10 + 5 * 3 - 1` 的结果
3. 判断 `10 > 5 && 3 < 5` 的结果是 true 还是 false
4. 用 for 循环打印 1 到 10 的所有偶数

### 提高题
5. 写一个函数，判断一个数是否为质数
6. 写一个函数，接收数组，返回数组中的最大值
7. 用数组的 `reduce` 方法计算 `[1, 2, 3, 4, 5]` 的乘积

---

## 12. 参考答案

### 基础题答案

```javascript
// 第1题
let name = "张三";
console.log(name);

// 第2题
console.log(10 + 5 * 3 - 1); // 24（注意运算符优先级）

// 第3题
console.log(10 > 5 && 3 < 5); // true

// 第4题
for (let i = 1; i <= 10; i++) {
    if (i % 2 === 0) {
        console.log(i);
    }
}
```

### 提高题答案

```javascript
// 第5题：判断质数
function isPrime(n) {
    if (n <= 1) return false;
    if (n <= 3) return true;
    for (let i = 2; i <= Math.sqrt(n); i++) {
        if (n % i === 0) return false;
    }
    return true;
}

// 第6题：数组最大值
function findMax(arr) {
    return arr.reduce((max, num) => num > max ? num : max, arr[0]);
}

// 第7题：数组乘积
function product(arr) {
    return arr.reduce((acc, num) => acc * num, 1);
}

console.log(product([1, 2, 3, 4, 5])); // 120
```
