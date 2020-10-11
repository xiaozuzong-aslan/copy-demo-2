typeScript 原始数据类型
string number bolean null undefined enum symbol

空值一般采用void void可以表示变量也可以表示函数无返回值

typeScript 中的联合类型
var muchType:string |number = 'hello'



typeScript 中对象类型接口

可以描述类的一部分抽象行为，也可以描述对象的结构形状
接口一般首字母大写 有的编程语言建议接口的名字加上I前缀
//通过interface 定义接口
interface Istate{
    name:string,
    age:number
}
var obj1:Istate = {name:'张三',age:'xxx'}
//属性个数不确定的时候
interface Istate3 {
    name:string,
    age?:number,//可以为空
    [propName:string]:any
}
var obj3:Istate3 = {name:'xxx',age:10,sex:'男'，isMarry:true}

//只读属性
interface Istate4 {
    readonly name:string, //只读的
    age?:number,//可以为空
    [propName:string]:any
}
const obj4:Istate4 = {name:'xxx',age:10,sex:'男'，isMarry:true}

//数组表示法
var arr:number[] =[1,2,3]
var arr:string[] =['1','2','3']
//泛型Array <elemType>表示法
var arrType:Array<number> = [1,2,3]
var arrType2:Array<string> = ['1','2','3']
var arrType3:Array<any> = [1,'2',true]
//接口表示法
interFace Iarr{
    [index:number]:number
}
var arrType:Iarr = [1,2,3]

//函数类型
函数约束 有函数本身的参数约束
申明式类型的函数
function Type(name:string,age:number):number{
    return number
}
var ageNum:number = functype('张三',18)

//函数参数不确定
function funType2(name:string,age:number,sex?:string):number{
    return age
}
var ageNum2:number = funcType2('张三',18,'男')

//函数参数的默认值
function funcType3(name:string='张三'，age:number = 18):number{
    return age
}



// 断言  只能断言联合类型中存在的类型
类型断言可以用手动指定一个值的类型
语法<类型>值 或者值as类型
在tsx语法(React的jsx语法的ts版) 必须采用后面的一种
类型断言不是类型转换，断言成一个联合类型中不存在的类型是不允许的

function get (name:string|number){
    //return (name as string).length
     return (<string>name).length
}

# 合并4个子组件的方法   记得用Partial<typeof Obj>

