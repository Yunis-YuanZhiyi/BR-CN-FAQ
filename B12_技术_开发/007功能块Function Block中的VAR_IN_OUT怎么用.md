# VAR_IN_OUT接口是什么
- 一个 `VAR_IN_OUT` variable 是一个输入/输出变量，它是Function Block接口的一部分，用作正式的按引用传递参数。
- ![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420171138782.png)
- VAR_IN_OUT能够实现的效果为，通过功能块直接操作外部的变量，对外部变量进行直接修改。
- 输入/输出变量 (VAR_IN_OUT) 将转变成为一个指针。因此，在调用时不能对它们赋值常数，而且不能进行外部的读或写操作。
- 在调用有VAR_IN_OUT类型的功能块时，必须如下图，VAR_IN_OUT变量赋值与函数调用同时执行。
- ![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420171309463.png)
# 什么情况下建议使用VAR_IN_OUT类型接口
- 操作的数据类型是公用的数据类型，则使用VAR_IN_OUT可节省VAR_IN与VAR_OUT两次赋值操作
- 操作的数据类型比较大，使用VAR_IN_OUT可以减少整体数据的赋值操作
- 使用 VAR_INPUT 和 VAR_OUTPUT 会造成占用过多的内存，为此，在功能块编程时，可尽量使用 VAR_IN_OUT 替代，减少对存储区的占用

# 如何使用VAR_IN_OUT
## A.功能块操作
### A.1. 在库中定义一个VAR_IN_OUT接口
- ![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420172621853.png)
### A.2.在此库中编写代码
- 与常规变量一样使用
- 例如下图中代码案例即为，调用一次功能块，则guTest这个变量的数值将增加
- ![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420172739198.png)
## B.代码调用
### B.1.声明与VAR_IN_OUT接口类型同类型的变量
- ![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420173736921.png)

### B.2 调用方式如下，VAR_IN_OUT接口必须与函数同时调用
- ![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420172927908.png)
## C.注意事项
![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/image-20230420173722229.png)

## D.效果
![](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/TestVAR_IN_OUT.gif)

# 测试Demo
- [Demo文件](FILES/007功能块Function%20Block中的VAR_IN_OUT怎么用/Test_VAR_IN_OUT.7z)

# 异常使用时报错信息
## 1177
- Short text
    - No external access to VAR_IN_OUT parameter `<Name>` of `<Function block>`. 
- Error description
    - When calling a function block, the address of the current parameter is specified for VAR_IN_OUT parameters instead of the value. This allows the value of the current parameter in the function block to be changed.
    - A VAR_IN_OUT parameter is only permitted to be used when calling a function block; direct access using the instance variable is not possible.
    - In Automation Basic, an alias function block call cannot be assigned to a VAR_IN_OUT parameter. Assignment to a VAR_IN_OUT parameter of a function block is only possible with a normal function block call. In a normal function block call, all parameters are specified in the line in which the call is made.
- Suggestion for error correction
    - In Automation Basic, replace the alias function block call of a function block with a VAR_IN_OUT parameter with a normal function block call.


 

