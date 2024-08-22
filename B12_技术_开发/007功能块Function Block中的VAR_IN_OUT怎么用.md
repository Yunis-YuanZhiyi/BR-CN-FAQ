> Tags: #开发
- [1 B12.007.功能块Function Block中的VAR_IN_OUT怎么用](#_1-b12007%E5%8A%9F%E8%83%BD%E5%9D%97function-block%E4%B8%AD%E7%9A%84var_in_out%E6%80%8E%E4%B9%88%E7%94%A8)
- [2 VAR_IN_OUT接口是什么](#_2-var_in_out%E6%8E%A5%E5%8F%A3%E6%98%AF%E4%BB%80%E4%B9%88)
- [3 什么情况下建议使用VAR_IN_OUT类型接口](#_3-%E4%BB%80%E4%B9%88%E6%83%85%E5%86%B5%E4%B8%8B%E5%BB%BA%E8%AE%AE%E4%BD%BF%E7%94%A8var_in_out%E7%B1%BB%E5%9E%8B%E6%8E%A5%E5%8F%A3)
- [4 如何使用VAR_IN_OUT](#_4-%E5%A6%82%E4%BD%95%E4%BD%BF%E7%94%A8var_in_out)
	- [4.1 A.功能块操作](#_41-a%E5%8A%9F%E8%83%BD%E5%9D%97%E6%93%8D%E4%BD%9C)
		- [4.1.1 A.1. 在库中定义一个VAR_IN_OUT接口](#_411-a1-%E5%9C%A8%E5%BA%93%E4%B8%AD%E5%AE%9A%E4%B9%89%E4%B8%80%E4%B8%AAvar_in_out%E6%8E%A5%E5%8F%A3)
		- [4.1.2 A.2.在此库中编写代码](#_412-a2%E5%9C%A8%E6%AD%A4%E5%BA%93%E4%B8%AD%E7%BC%96%E5%86%99%E4%BB%A3%E7%A0%81)
	- [4.2 B.代码调用](#_42-b%E4%BB%A3%E7%A0%81%E8%B0%83%E7%94%A8)
		- [4.2.1 B.1.声明与VAR_IN_OUT接口类型同类型的变量](#_421-b1%E5%A3%B0%E6%98%8E%E4%B8%8Evar_in_out%E6%8E%A5%E5%8F%A3%E7%B1%BB%E5%9E%8B%E5%90%8C%E7%B1%BB%E5%9E%8B%E7%9A%84%E5%8F%98%E9%87%8F)
		- [4.2.2 B.2 调用方式如下，VAR_IN_OUT接口必须与函数同时调用](#_422-b2-%E8%B0%83%E7%94%A8%E6%96%B9%E5%BC%8F%E5%A6%82%E4%B8%8B%EF%BC%8Cvar_in_out%E6%8E%A5%E5%8F%A3%E5%BF%85%E9%A1%BB%E4%B8%8E%E5%87%BD%E6%95%B0%E5%90%8C%E6%97%B6%E8%B0%83%E7%94%A8)
	- [4.3 C.注意事项](#_43-c%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9)
	- [4.4 D.效果](#_44-d%E6%95%88%E6%9E%9C)
- [5 测试Demo](#_5-%E6%B5%8B%E8%AF%95demo)
- [6 异常使用时报错信息](#_6-%E5%BC%82%E5%B8%B8%E4%BD%BF%E7%94%A8%E6%97%B6%E6%8A%A5%E9%94%99%E4%BF%A1%E6%81%AF)
	- [6.1 1177](#_61-1177)

# 1 B12.007.功能块Function Block中的VAR_IN_OUT怎么用

# 2 VAR_IN_OUT接口是什么

- 一个 `VAR_IN_OUT` variable 是一个输入/输出变量，它是Function Block接口的一部分，用作正式的按引用传递参数。
    - ![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420171138782.png)
- VAR_IN_OUT能够实现的效果为，通过功能块直接操作外部的变量，对外部变量进行直接修改。
- 输入/输出变量 (VAR_IN_OUT) 将转变成为一个指针。因此，在调用时不能对它们赋值常数，而且不能进行外部的读或写操作。
- 在调用有VAR_IN_OUT类型的功能块时，必须如下图，VAR_IN_OUT变量赋值与函数调用同时执行。
- ![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420171309463.png)

# 3 什么情况下建议使用VAR_IN_OUT类型接口

- 操作的数据类型是公用的数据类型，则使用VAR_IN_OUT可节省VAR_IN与VAR_OUT两次赋值操作
- 操作的数据类型比较大，使用VAR_IN_OUT可以减少整体数据的赋值操作
- 使用 VAR_INPUT 和 VAR_OUTPUT 会造成占用过多的内存，为此，在功能块编程时，可尽量使用 VAR_IN_OUT 替代，减少对存储区的占用

# 4 如何使用VAR_IN_OUT

## 4.1 A.功能块操作

### 4.1.1 A.1. 在库中定义一个VAR_IN_OUT接口

- ![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420172621853.png)

### 4.1.2 A.2.在此库中编写代码

- 与常规变量一样使用
- 例如下图中代码案例即为，调用一次功能块，则guTest这个变量的数值将增加
    - ![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420172739198.png)

## 4.2 B.代码调用

### 4.2.1 B.1.声明与VAR_IN_OUT接口类型同类型的变量

- ![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420173736921.png)

### 4.2.2 B.2 调用方式如下，VAR_IN_OUT接口必须与函数同时调用

- ![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420172927908.png)

## 4.3 C.注意事项

![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420173722229.png)

## 4.4 D.效果

![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/TestVAR_IN_OUT.gif)

# 5 测试Demo

- [Demo文件](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/Test_VAR_IN_OUT.7z)

# 6 异常使用时报错信息

## 6.1 1177

- Short text
    - No external access to VAR_IN_OUT parameter `<Name>` of `<Function block>`.
- Error description
    - When calling a function block, the address of the current parameter is specified for VAR_IN_OUT parameters instead of the value. This allows the value of the current parameter in the function block to be changed.
    - A VAR_IN_OUT parameter is only permitted to be used when calling a function block; direct access using the instance variable is not possible.
    - In Automation Basic, an alias function block call cannot be assigned to a VAR_IN_OUT parameter. Assignment to a VAR_IN_OUT parameter of a function block is only possible with a normal function block call. In a normal function block call, all parameters are specified in the line in which the call is made.
- Suggestion for error correction
    - In Automation Basic, replace the alias function block call of a function block with a VAR_IN_OUT parameter with a normal function block call.
