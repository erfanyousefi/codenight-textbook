# درس‌نامه جامع جاوااسکریپت برای بک‌اند و شی‌گرایی — ویژه دانشجویان

این درس‌نامه به صورت جامع، مباحث کلیدی جاوااسکریپت در حوزه بک‌اند (Node.js) و مفاهیم شی‌گرایی را برای دانشجویان شرح می‌دهد؛ با مثال‌های عملی و تمرین‌های پیشنهادی برای تسلط بیشتر.

---

## بخش اول: مبانی جاوااسکریپت برای بک‌اند

### ۱. مقدمات

- **برنامه‌نویسی:** هنر حل مسئله با کد
- **بک‌اند:** پردازش داده، ارتباط با دیتابیس و مدیریت منطق سرور  
- **ابزار مورد نیاز:**  
    1. Node.js  
    2. VSCode  
    3. ترمینال (Terminal)

**تمرین:**  
Node.js را نصب کنید، سپس دستور زیر را اجرا کنید:
```bash
node -v
```
یک فایل به نام `hello.js` بسازید و اجرا کنید:
```js
console.log("Hello World!");
```

---

### ۲. انواع داده

- **Number, String, Boolean, Undefined, Null, Object, Array**
- عملیات عددی و رشته‌ای

**تمرین:**  
متغیرهایی با انواع مختلف ساخته و نوع آن‌ها را چک کنید:
```js
let a = 20;
let b = "Ali";
let c = true;
let d;
let e = null;
let f = [1, 2, 3];
console.log(typeof a, typeof b, typeof c, typeof d, typeof e, typeof f);
```

---

### ۳. متغیرها، قوانین نام‌گذاری و Scope

- `let`, `const`, `var`
- قواعد نام‌گذاری
- مفهوم **Scope**: محدودیت دسترسی متغیرها  
- **مقایسه:**  
    - `null` : مقدار تهی با هدف خاص  
    - `undefined` : تعریف نشده

**تمرین:**  
تفاوت متغیرهای Local و Global
```js
let globalVar = 10;
function test() {
  let localVar = 5;
  console.log(globalVar); // ok
  // console.log(localVar); // خارج از تابع: خطا
}
test();
```
---

### ۴. دستورات شرطی و عملگرهای منطقی

- `if/else if/else`, `switch-case`, عملگر سه‌تایی
- مقادیر **Truthy/Falsy**
- عملگرها: `&&`, `||`, `!`

**تمرین:**  
بررسی سن و نمایش پیام مناسب:
```js
let age = 19;
if(age >= 18){
  console.log("دانشجو مجاز به ورود است");
} else {
  console.log("ورود غیرمجاز");
}
```

---

### ۵. حلقه‌ها (Loops)

- انواع: `for`, `for...of`, `for...in`, `while`, `do-while`
- دستورات: `continue`, `break`

**تمرین:**  
نمایش اعداد زوج در بازه 1 تا 20:
```js
for(let i=1; i<=20; i++){
    if(i % 2 === 0){
        console.log(i);
    }
}
```

---

### ۶. توابع (Functions)

- تعریف تابع، Arrow function (`=>`)
- پارامتر پیش‌فرض، بازگشت مقدار (`return`)
- توابع بازگشتی و تو در تو

**تمرین:**  
تابع جمع اعداد، تابع فاکتوریل:
```js
function factorial(n){
  if(n<=1) return 1;
  return n * factorial(n-1);
}
console.log(factorial(5)); // 120
```
Arrow function:
```js
const add = (a, b=0) => a + b;
console.log( add(2, 3) );
```

---

### ۷. آرایه‌ها (Arrays) و متدهای مهم

- عملیات پایه: `push`, `pop`
- متدهای پیشرفته:  
    - `splice`, `slice`, `forEach`, `map`, `filter`, `reduce`, `sort`, `find`

**تمرین:**  
استفاده از چند متد:
```js
let nums = [1, 2, 3, 4, 5];
let even = nums.filter(n => n % 2 === 0);
let squares = nums.map(n => n*n);
let sum = nums.reduce((acc, cur) => acc + cur, 0);
console.log(even, squares, sum);
```

---

### ۸. اشیاء (Objects) و متدهای مهم

- تعریف شیء، دسترسی (`dot`/`bracket` notation)
- `for...in` برای پیمایش properties
- استفاده از `Object.assign`
- تعریف متد روی شیء

**تمرین:**  
ساخت Object با متد:
```js
let user = {
  name: "Sara",
  age: 22,
  sayHello: function() {
    console.log("سلام " + this.name);
  }
};
user.sayHello();
```

---

### ۹. مفاهیم پیشرفته‌تر

- کار با JSON: `JSON.stringify`, `JSON.parse`
- Rest (`...args`) و Spread (`...`)
- **Hoisting:** بالا رفتن تعریف توابع و متغیرها  
- **IIFE:** تابع فوری اجراشونده

**تمرین:**  
Rest/Spread و IIFE
```js
function sum(...args){
    return args.reduce((a,b)=>a+b,0);
}
console.log( sum(1,2,3,4) );

let obj1 = { a: 1 }; 
let obj2 = { b: 2 };
let merged = { ...obj1, ...obj2 };

(function(){
    console.log("این یک IIFE است");
})();
```

---

#### راهنمای کار

- تست و دیباگ با `console.log`
- نظم در پوشه‌بندی و مستندسازی
- تسلط بر این مباحث، پایه موفقیت در Node.js است.

---

## بخش دوم: شی‌گرایی در جاوااسکریپت (Object-Oriented Programming – OOP)

### ۱۰.۱. مفاهیم اولیه

- **Object:** محفظه داده و رفتار
- **Class:** قالب یا نقشه ساختنمونه‌ها
- **Instance:** شیء ساخته‌شده از یک کلاس
- **Property:** ویژگی داده‌ای
- **Method:** رفتار/عملکرد

---

### ۱۰.۲. تعریف شیء به روش سنتی

```js
let car = {
    brand: "Peugeot",
    model: 206,
    start: function() {
        console.log(this.brand + " روشن شد!");
    }
};

car.start();  // خروجی: Peugeot روشن شد!
```
**تمرین:**  
Object student با property `name`, آرایه `scores`، متدی برای محاسبه معدل بسازید.

---

### ۱۰.۳. سازنده شیء (Constructor Function)

```js
function Person(name, age) {
    this.name = name;
    this.age = age;
    this.sayHello = function() {
        console.log("سلام، من " + this.name + " هستم.");
    }
}

const p1 = new Person("Sara", 25);
p1.sayHello();
```
**تمرین:**  
تابع سازنده Book بنویسید که `title`, `author` بگیرد و متدی برای نمایش اطلاعات داشته باشد.

---

### ۱۰.۴. کلاس‌ها (Class) در جاوااسکریپت مدرن

```js
class Animal {
    constructor(type, sound) {
        this.type = type;
        this.sound = sound;
    }
    makeSound() {
        console.log(`${this.type} says ${this.sound}`);
    }
}

const cat = new Animal("Cat", "Meow");
cat.makeSound();
```
- **constructor:** متد مخصوص مقداردهی اولیه
- **this:** اشاره به نمونه ساخته‌شده

**تمرین:**  
کلاس Student با property `name` و آرایه `scores` و متدهای اضافه‌کردن/حذف نمره و محاسبه معدل.

---

### ۱۰.۵. وراثت (Inheritance)

```js
class Vehicle {
    constructor(brand) { this.brand = brand; }
    start() { console.log(this.brand + " استارت زد!"); }
}
class Car extends Vehicle {
    constructor(brand, model) {
        super(brand);
        this.model = model;
    }
    info() { console.log(`${this.brand} ${this.model}`); }
}

const pride = new Car("SAIPA", "Pride");
pride.start(); // "SAIPA استارت زد!"
pride.info();  // "SAIPA Pride"
```
**تمرین:**
- کلاس `Employee` با property name و متدی برای چاپ نام بسازید.
- کلاس `Programmer` از `Employee` ارث‌بری کند و property زبان و متد introduce داشته باشد.

---

### ۱۰.۶. چندریختی (Polymorphism)

```js
class Animal {
    speak() { console.log("یک حیوان صدا داد!"); }
}
class Dog extends Animal {
    speak() { console.log("سگ واق واق کرد!"); }
}
const a = new Animal();
const d = new Dog();
a.speak(); // یک حیوان صدا داد!
d.speak(); // سگ واق واق کرد!
```

---

### ۱۰.۷. کپسوله‌سازی (Encapsulation)

(ویژگی خصوصی با `#` (ES2022+))
```js
class Account {
    #balance = 0;
    deposit(amount) { this.#balance += amount; }
    getBalance() { return this.#balance; }
}

let acc = new Account();
acc.deposit(1000);
console.log(acc.getBalance()); // 1000
```

---

### ۱۰.۸. متدها و پراپرتی‌های static

```js
class MathUtil {
    static sum(a,b) { return a+b; }
}
console.log( MathUtil.sum(2,5) ); // 7
```
**تمرین:**  
متد static برای ساخت Employee تنها با نام (بدون new) پیاده‌سازی کنید.

---

### تمرین‌های ترکیبی و پروژه‌ای

1. **کلاس BankAccount**
   - پراپرتی خصوصی `#balance`
   - متدهای واریز، برداشت، نمایش مانده
2. **کلاس SavingAccount** (وراثت از BankAccount)
   - متد پرداخت سود
3. **پروژه:**  
   سیستم مدیریت دانش‌آموز: کلاس Student و School. افزودن/حذف دانش‌آموز و محاسبه معدل کلی دانش‌آموزان.

---

## راهنمایی پایانی

- مرتباً تست و دیباگ کنید (`console.log`)
- موارد گنگ را بپرسید تا رفع ابهام شود.
- تسلط بر این بخش‌ها، نقطه شروع قوی برای Node.js و پروژه‌های بک‌اند است.

---

## منابع کمکی

- [MDN JavaScript Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

---

موفق باشید! 🌱
