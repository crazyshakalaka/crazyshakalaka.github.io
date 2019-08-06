# Typescript-接口interface

[TOC]



#### 定义数组的方式：

```typescript
let arr:number[]=[1,1,2]; //还有另外的一种格式：如下
let arr:Array<number>=[1,23,2];
```

#### interface接口定义数组：可索引接口（对数组的约束）

```typescript
interface Animal{
    [index:number]:number
}
let arr:Animal=[1,2,3,4];
console.log(arr[1]);
```

#### interface接口索引（对对象的约束）
```typescript
interface obj{
    [index:string]:string
}
let arr:obj={name:'张三',age:'20'};// console.log输出时undifined
```

#### 类类型接口（对类的约束）和抽象类有点相似

```typescript
interface Animal{
    name : string;
    eat(str:string):void;
}
class Dog implements Animal{

    name  : string;
    constructor(name:string){
        this.name = name;
    }
    eat(){
        console.log(this.name+'吃粮食');
        
    }
}
class Cat implements Animal{
    name : string;
    constructor(name:string){
        this.name = name;
    }
    eat(food:string){
        console.log(this.name+'吃'+food);
        
    }
}
let w = new Dog('旺财');
w.eat();
let c= new Cat('小花')
c.eat('老鼠')
//必须按照接口来写，但是可以多方法，但是接口有的必须有
```

#### 接口的扩展也就是接口继承接口

```typescript
interface Animal{
    eat(food:string):void;
}
interface Person extends Animal{
    work(work1:string):void;
}
class Xue implements Person{
    name : string;
    constructor(name:string){
        this.name = name;
    }
    eat(food:string){
        console.log(this.name+'吃'+food);
        
    }
    work(work1:string){
        console.log(this.name+'写'+work1);
        
    }
}
let x = new Xue('薛奎浩');
x.eat('火锅');
x.work('代码')
```

#### 既继承接口也继承类

```typescript
interface Animal{
    eat(food:string):void;
}
interface Person extends Animal{
    work(work1:string):void;
}
class program{
    name : string;
    constructor(name:string){
        this.name = name;
    }
    coding(code:string){
        console.log(this.name+code);
        
    }
}

class Xue extends program implements Person{

    constructor(name:string){
        super(name);
    }
    eat(food:string){
        console.log(this.name+'吃'+food);
        
    }
    work(work1:string){
        console.log(this.name+'写'+work1);
        
    }
}
let x = new Xue('薛奎浩');
x.eat('火锅');
x.work('代码')
x.coding('写ts代码')
```



