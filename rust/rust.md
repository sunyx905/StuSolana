# 入门

cargo命令

cargo new packageName



# 猜数字

定义变量

```rust
  let mut guess = String::new();
    let nums1 =1;
    let mut nums2 =2;   mut将变量标记为可变的
    nums1=2;   err
    nums2=3;   ok
```



添加外部库=crate

在tomlz文件中

库名=“版本号”

rand=xxxx

![image-20250624201012815](F:\code\codeNote\solana\rust\rust.assets\image-20250624201012815.png)

使用命令

cargo add rand xxxx版本号



cargo.lock文件记录了导入的相关依赖=crate



# 相关概念

静态static  编译时确定变量属性。

编译型语言：将代码编译成电脑可执行的文件。



stack栈内存和堆heap内存

栈 先进后出 

heap随机一块空间 有指针



# 基础语法和数据类型

## scalar标量类型

integer float boolean character

```rust
let a :u8 = 1;
let b = 1.1;
let c = true;
let d = 'a';
```

## compound

tuple 元组 不同类型的组合   长度固定

array 数组 相同类型的组合   长度固定

 

```rust
let tup =(1,2.2,'a');
//创建时 长度确定。

println!("{}",tup.0);

let arr = [1,2,3,4,5];

let ayy:[u32;3] = [1,6,7];

let auu =[3;5]; //auu数组里包含 5个3
println!("{}",auu[0]);
```



# 函数

函数和变量的命名规则 小写_拼接

fn 函数名(参数) -> 返回值类型 {



}

```rust
参数的类型要确定 xx:类型  返回值的类型要声明 
fn to_print(value:String){
    println!("{}", value);
}

fn add(a:u32,b:u32)->u32{
    a+b                     表达式==return a+b;  加上;就不会返回了
    // return a+b;
}
```



# 控制流

类型的三元表达式

```rust
let flag = true;
let res = if flag {1} else {2};
                   1        2   1和2的类型要相同因为，rust是强类型语言，需要在编译时确定属性的类型。
```



if

```rust
let mut a = 2; 

if a==1{              判断条件
    println!("1");
}
else if a==2{
    println!("2");
}
else{
    println!("else");
}
```



循环

loop

```rust
let mut a = 1;

res接受 break 后返回的值；
break结束循环
let res = loop{
    if(a == 10){
        break "is over";
    }
    println!("a is {a}");
    a = a + 1;
};

loop嵌套
"forntier";
    loop
    { loop {
        if (a == 10) {
            break a;
        }
        if(a==15){
            break "forntier";
        }
        println!("a is {a}");
        a = a + 1;
    }; 
    
    }

给外层loop循环一个标签，  break "forntier"; 就会结束外部的循环
```



while

```rust
let a = 1;
while a<10  {         while  判断的条件
    print!(" ");
}
```



for 通常用于数组的遍历

```rust
let arr = [1,2,3,4,5,6,7,8,9,10];


for i in arr{
    print!("{} ",i);
}
```



# 所有权

一组规则，在编译时使用这套规则检查。

三大原则

1. **每个值都有一个所有者（owner）**
2. **同一时间只能有一个所有者**
3. **当所有者离开作用域时，值将被丢弃（dropped）**