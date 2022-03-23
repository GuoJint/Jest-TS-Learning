# type annotation 类型注解 && type inference 类型推断  增加健壮性
1. 静态类型： 定义类型后，类型不可更改
``` typescript
let count : number = 1
```
2. 自定义静态类型： 
``` typescript
interface xiaohong {
  name: string,
  age: number
}
const xiaohong: xiaohong = {
  name: 'sss',
  age: 12
}

// 对象类型(对象，数组，类，函数)

// 利用静态类型限制数组或对象中的值
const obj: {
  name: string,
  age: number
} = {
  name: '大大',
  age: 18
}
const arr: string[] = ['ss','dd']
const arr: (string | number)[] = [1,'string']

//类型别名
type Lady = { name:string,age:number }
// 类
class Madam {
  name: string;
  age: number;
}
const arr: Lady[] = {
  { name:'string',age:1 },
  { name:'string',age:1 }
}


// 必须为Person的实例
class Person {}
const dajiao : Person = new Person()

// 必须是一个函数且返回字符串
const getDate: ()=>string = () => {return 'dajioa'}


// 能够自动推断出类型的情况是类型推断，有些情况不能够推断出来就需要类型注解
// 两者为结合使用
// 能推断就推断，不能推断就进行注解!!!!!!

// 函数返回注解， 限定了返回时的类型
function getTotal (one: number , two : number) : number {
  return one + two
}
const total = getTotal(1, 2)

// 对象形式只能通过: {}形式来添加注解
function add ({one, two} : { one: number, two:number }) {
  return one + two
}
cosnt total = add({one:1,tow:2})

function say() : void {
  console.log('无返回类型')
}

// :never 死循环和永远执行不完的

```

