# JavaScript Scope and Hoisting

![JavaScript Logo](https://via.placeholder.com/800x200?text=JavaScript+Scope+and+Hoisting)

Understanding **Scope** and **Hoisting** is fundamental for mastering JavaScript. This document provides explanations and examples in English and Russian.

Понимание **области видимости** и **всплытия** — это основа для освоения JavaScript. Этот документ содержит объяснения и примеры на английском и русском языках.

---

## Table of Contents / Оглавление

1. [What is Scope? / Что такое область видимости?](#what-is-scope--что-такое-область-видимости)
   - [Global Scope / Глобальная область видимости](#global-scope--глобальная-область-видимости)
   - [Local Scope / Локальная область видимости](#local-scope--локальная-область-видимости)
   - [Block Scope / Блочная область видимости](#block-scope--блочная-область-видимости)
2. [What is Hoisting? / Что такое всплытие?](#what-is-hoisting--что-такое-всплытие)
   - [How Hoisting Works / Как работает всплытие](#how-hoisting-works--как-работает-всплытие)
3. [Examples / Примеры](#examples--примеры)
4. [Conclusion / Заключение](#conclusion--заключение)

---

![Scope](https://miro.medium.com/v2/resize:fit:1400/1*naPPWUJjDMmKXZzsWopOqQ.jpeg)

## What is Scope? / Что такое область видимости?

Scope determines where variables, constants, and functions are accessible in your code.

Область видимости определяет, где переменные, константы и функции доступны в коде.

---

### Global Scope / Глобальная область видимости

Variables declared outside any function or block are in the **global scope**. They are accessible throughout the program.

Переменные, объявленные вне функций или блоков, находятся в **глобальной области видимости**. Они доступны во всей программе.

# Function Scope

**Function Scope** refers to the context in which variables are accessible during the execution of a program. In JavaScript, variables declared inside a function are only accessible within that function. These are called **local variables**.

![](https://soshace.com/wp-content/uploads/2023/04/scope-schema-1200.jpg)

### Example (in JavaScript):
```javascript
function myFunction() {
    let localVariable = "I am local!"; // This variable is only accessible inside myFunction
    console.log(localVariable); // Выведет: Я локальная переменная!
}

myFunction(); // Logs: I am local!

// console.log(localVariable); 
// Раскомментирование вызовет ошибку, так как localVariable находится вне области видимости


# Block Scope

**Block Scope** refers to the context in which variables are accessible within a specific block, such as within an `if`, `for`, or `while` statement. Variables declared inside a block using `let` or `const` are only accessible within that block. This is different from function scope, where variables are accessible throughout the entire function.

### Example (in JavaScript):
```javascript
{
    let blockVariable = "I am block-scoped!"; // This variable is only accessible inside this block
    console.log(blockVariable); // Выведет: Я локальная переменная блока!
}

// console.log(blockVariable); 
// Раскомментирование вызовет ошибку, так как blockVariable находится вне области видимости блока

if (true) {
    let blockIfVariable = "I am inside an if block!"; // Эта переменная доступна только внутри этого блока if
    console.log(blockIfVariable); // Выведет: Я внутри блока if!
}

// console.log(blockIfVariable); 
// Раскомментирование вызовет ошибку, так как blockIfVariable находится вне области видимости блока if



#### Example / Пример:

```javascript
let globalVar = "I am global";

function showGlobalVar() {
  console.log(globalVar); // Accessible here
}

showGlobalVar();
console.log(globalVar); // Accessible here too
