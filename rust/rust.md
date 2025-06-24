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