### 1. 简介
``` python
微软开发的javascript的超集，添加了新的遵循es6的语法。
由于Angular2是基于typescript的，受到微软和谷歌的支持。
优势：
(1)支持es6规范；
(2)欠打的IDE支持（类型检测、语法提示）；
(3)Angular2的开发语言
```
### 2. 搭建Typescript开发环境
``` python
由于部分浏览器对es6的不支持，我们用到了compiler编译器，需要把Typescript编译成javascript
线上搭建：http://www.typescriptlang.org/play/index.html
本地搭建：
安装typescript：npm i -g typescript
查看安装版本： tsc --version
```
### 3. 字符串新特性
``` python
(1)多行字符串``
(2)字符串模板
·${变量名/方法}`
(3)自动拆分字符串
```
### 4. 参数新特性
``` python
在参数名称后面使用冒号来指定参数的类型
(1)
var myname: string = 'meng zong';
var alias = 'meng zong';
// alias = 13;
var str:any = 'meng zong';
str = 13;

// string, number, any, void(用来声明方法不需要返回值的)
// 在变量或方法后边可以声明前三个类型
// function test(): void{
//     return '';
// }

// 自定义类型
class Person{
    name: string;
    age: number;
}

var zhangsan: Person = new Person();
zhangsan.name = '张三';
zhangsan.age = 18;

(2)默认参数：在参数声明后面用等号来指定参数的默认值
var myname: string = 'meng zong';
function test(a: string, b: string, c: string="jojo") {
    console.log(a);
    console.log(b);
    console.log(c);
}
test('xxx', 'yyy', 'zzz');
test('xxx', 'yyy');
(3)可选参数：在方法的参数声明后面用问号来标明此参数为可选参数
```
### 5.函数新特性
``` python
(1)Rest and Spread操作符：
用来声明任意数量的方法参数
(2)generator函数：
控制函数的执行过程，手工暂停和恢复代码执行
function* doSomething(){
    console.log('start');

    yield;
    
    console.log('finish');
}

var func1 = doSomething();
func1.next();
func1.next();
(3)destructuring析构表达式
通过表达式将对象或数组拆解成任意数量的变量：
对象：
    function getStock() {
        return {
            code: 'IBM',
            price: {
                price1: 200,
                price2:400
            },
            aaa: 'xx',
            bbb: 'hhh'
        }
    }
    
    var {code:codex, price:{price2}} = getStock();
    console.log(codex,price2);
    
    
数组：
    var array1 = [1,2,3,4];
    //var [,,number1,number2] = array1;
    // var [number1,number2,...others] = array1;
    // console.log(number1,number2,others);
    function doSomething([number1,number2,...others]){
        console.log(number1,number2,others);
    }
    doSomething(array1);
```
### 6. 表达式和循环
``` python
(1)箭头表达式
用来声明匿名函数，消除传统的匿名函数的this指针问题
    var sum = (num1, num2) => num1 + num2;
    var sum = (num1, num2) => {
        return num1 + num2;
    };
(2) forEach for..in（支持对象和数组） for...of 
eg: 
var arr = [1,2,3,4];
arr.desc = 'four number';
forEach()不支持break，continue;还有不会输出的值desc值；
for...in不支持break，continue;会输出desc值；
for...of可以break,continue,不会输出desc值
```
### 7. 面向对象特性
``` python
(1) 类：
class People {
    constructor(public name:string) {  // 需要明确声明
    }
    /*constructor(name:string) {  // 如果不声明，会在eat方法中访问不到
    }*/
    eat() {
        console.log('eating');
    }
}

class Emplyee extends People {
    code: string;
    constructor(name: string, code: string){
        super(name);
        this.code = code;
    }
    work() {
        super.eat();
        this.doWork();
    };
    private doWork() {
        console.log('I am working')
    }
}

var p1 = new People('betman');
p1.eat();

var e1 = new Emplyee('name', '1');
e1.work();

// 访问控制符public(默认)、private(只有在类的内部访问到)、protected(只能在类的内部和子类能访问到)

(2)泛型（generic）
参数化的类型，一般用来限制集合的内容
class People {
    constructor(public name:string) {  // 需要明确声明
    }
    /*constructor(name:string) {  // 如果不声明，会在eat方法中访问不到
    }*/
    eat() {
        console.log('eating');
    }
}

class Employee extends People {
    code: string;
    constructor(name: string, code: string){
        super(name);
        this.code = code;
    }
    work() {
        super.eat();
        this.doWork();
    };
    private doWork() {
        console.log('I am working')
    }
}
var workers: Array<People> = []; // 泛型的意思就是指定数据类型
workers[0] = new People('zhangsan');
workers[1] = new Employee('lisi', '2');
var p1 = new People('betman');
p1.eat();

var e1 = new Employee('name', '1');
e1.work();

// 访问控制符public(默认)、private(只有在类的内部访问到)、protected(只能在类的内部和子类能访问到)
(3)接口(Interface)：
用来建立某种代码约定，使得其它开发者在调用某个方法或创建的新的类时必须遵循接口的代码约定
```