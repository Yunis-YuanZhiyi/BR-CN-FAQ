# 现象
![](FILES/505%20Expect%20command%20line%20option%20instead%20of%20Name/image-20230217010334901.png)
# 原因
- 使用Automation Studio 4.2编译库文件，其中库的描述信息中包含了中文信息，如下图所示：
![](FILES/505%20Expect%20command%20line%20option%20instead%20of%20Name/image-20230217010434153.png)
> 注意：Function/Function Block函数名的说明信息包含中文不会导致报错

# 解决方式
- 方式一：使用高版本的AS软件，例如AS4.7编译则不会报错
- 方式二：将库名信息的注释信息调整为英文信息

