# TypeScript
### TypeScript is programming language, that contains js language, and adds functions that makes js strongly typed (means: the types are defined). 
___
## variables in ts
```ts
//-----------------------number type--------------------
let num1:number=7;
let num2:number=7.2;
let num3:number=NaN;
let num4:number=Number("7.2");  //num4 is 7.2
let num5:number=parseInt("7.2");  //num5 is 7
let num6:number=parseFloat("7.2");  //num6 is 7.2


//-----------------------string type--------------------
let str1:string="test";
let str2:string='test';
let str3:string=`test`;
let str4:string=num1.toString();


//-----------------------boolean type--------------------
let bool1:boolean=true;
let bool2:boolean=false;
let bool3:boolean=3<7 && 4>8;



//-----------------------any type-------------------------
let x:any=true;
x="Bob";
x=6;
x=8.8;
```

## Function in ts
```ts
function func(n1:number,n2:number):number{
    return n1+n2;
}
console.log(func(4,5));
```
## optional param
```ts
//-------------Default param--------------
function func(num1:number=8,num2:number=5):number{
   return num1+num2;
}
console.log(func(1));     //--> num1=1 num2=5
console.log(func(1,1));   //--> num1=1 num2=1
console.log(func());      //--> num1=8 num2=5


//-------------optional param--------------
function func(num1?:number,num2?:number):void{
   console.log(num1,num2);
}
console.log(func());      //--> num1=undefined num2=undefined
console.log(func(1,1));   //--> num1=1 num2=1
console.log(func(1));     //--> num1=1 num2=undefined
```

## function param
```ts
function printAll(...nums:number[]){
    for(let i:number=0; i<nums.length;i++){
        console.log(nums[i]);
    }
}
printAll();
printAll(1,2,3);
printAll(6,4);

```
## Any vs non-type
```ts
//variable 'x1' implicitly has an 'number' type
//because we assigned a value in the declaration line
let x1=4;


//variable 'x2' implicitly has an 'any' type,
//but a better type may be inferred from usage
let x2;
x2=6;
x2="a";


let x3:any=4;
x3="a";
```
## function type
```ts
let num:number;
num=3;

let f1:(n1: number,n2: number)=>number;
f1=(n1,n2)=>{return n1*n2};
```
## Enum
```ts
enum Color{
    RED,
    GREEN,
    BLUE
}

let c1:Color=Color.BLUE;
console.log(Color[c1]); //--> BLUE

let c2:Color=0;
console.log(Color[c2]); //--> RED

```
## Array and matrix
```ts
// arr1 and arr2 are the same - but 2 ways of defenition
let arr1:number[]=[1,2,3];
let arr2:Array<number>=new Array<number>(1,2,3);


// mat1 and mat2 are the same - but 2 ways of defenition
let mat1:number[][]=[ [1,2,3] , [1,2,3] ];
let mat2:Array<Array<number>>=new Array<Array<number>>(
    new Array<number>(1,2,3),
    new Array<number>(1,2,3)
);
```

## Basic class
```ts
class Cinema{
   private movieName:string;
   private movieLength:number;

   public constructor(movieName?:string,movieLength?:number){
        this.movieName=movieName;
        this.movieLength=movieLength;
   }

   public getDesc():string{
       return `${this.movieName} is ${this.movieLength} minutes`;
   }
}

let c1:Cinema=new Cinema();
let c2:Cinema=new Cinema("Capten Marvel",120);

console.log(c1.getDesc());  //--> undefined is undefined minutes
console.log(c2.getDesc());  //--> Capten Marvel is 120 minutes
```

## Set and get in oop
```ts

class Person{
    private _age:number;

    public set age(val:number){
        this._age=(val>120 || val < 0)?0 : val;
    }

    public get age():number{
        return this._age;
    }
}

let bob:Person=new Person;
bob.age=4;              // here we call the set
console.log(bob.age);   // here we cal the get
```

# Inheritance - super class
```ts
class A{
    public constructor(){
        console.log("I am in the A ctor");
    }
}

class B extends A{
    public constructor(){
        super();
        console.log("I am in the B ctor");
    }
}

let myB:A=new B();

/*
I am in the A ctor
I am in the B ctor
*/
```
## Interface
```ts
//access modifier cannot appear on a type member in interface
interface IFly{
    speed?:number;  // opional to implement this property - because the "?"
    startFly():void;
}

class Baloon implements IFly{
    name:string;
    startFly(): void {
        console.log("I am flying");
    }  
}

let x:IFly=new Baloon();
x.startFly();  //--> I am flying


// check if variable is instanceof a class
if(x instanceof Baloon){
    console.log("I am a baloon");
}


// 2 ways for down casting
let b1:Baloon=<Baloon>x;
let b2:Baloon=x as Baloon;
```








































































