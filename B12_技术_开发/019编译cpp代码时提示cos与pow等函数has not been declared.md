> Tags: #cpp

- [1 B12.019-编译cpp代码时提示cos与pow等函数has not been declared](#_1-b12019-%E7%BC%96%E8%AF%91cpp%E4%BB%A3%E7%A0%81%E6%97%B6%E6%8F%90%E7%A4%BAcos%E4%B8%8Epow%E7%AD%89%E5%87%BD%E6%95%B0has-not-been-declared)
- [2 原因](#_2-%E5%8E%9F%E5%9B%A0)
- [3 解决方式](#_3-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
	- [3.1 解决方式一：找到对应的math.h文件，进行调整](#_31-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%E4%B8%80%EF%BC%9A%E6%89%BE%E5%88%B0%E5%AF%B9%E5%BA%94%E7%9A%84mathh%E6%96%87%E4%BB%B6%EF%BC%8C%E8%BF%9B%E8%A1%8C%E8%B0%83%E6%95%B4)
	- [3.2 解决方式二：更改使用函数或指向自定义的头文件函数](#_32-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%E4%BA%8C%EF%BC%9A%E6%9B%B4%E6%94%B9%E4%BD%BF%E7%94%A8%E5%87%BD%E6%95%B0%E6%88%96%E6%8C%87%E5%90%91%E8%87%AA%E5%AE%9A%E4%B9%89%E7%9A%84%E5%A4%B4%E6%96%87%E4%BB%B6%E5%87%BD%E6%95%B0)
- [4 更新日志](#_4-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 B12.019-编译cpp代码时提示cos与pow等函数has not been declared

- 在常规电脑上正常编译通过的C++项目，在某些电脑上使用会提示一些基础的函数找不到
- ![](FILES/019编译cpp代码时提示cos与pow等函数has%20not%20been%20declared/image-20240701124628100.png)
- ![](FILES/019编译cpp代码时提示cos与pow等函数has%20not%20been%20declared/image-20240701125827337.png)

```
'::cos' has not been declared
'::atan2' has not been declared
'::acos' has not been declared
```

# 2 原因

- 在使用的cpp代码中，使用了atan2，cos，pow这些函数，最终引用到贝加莱系统自带的math.h头文件
- ![](FILES/019编译cpp代码时提示cos与pow等函数has%20not%20been%20declared/image-20240701130046972.png)
- 发现底层调用的math.h实现中，AS4.3软件下__math 68881与__math 6881宏定下的声明被屏蔽。
- ![](FILES/019编译cpp代码时提示cos与pow等函数has%20not%20been%20declared/image-20240701130117461.png)

# 3 解决方式

## 3.1 解决方式一：找到对应的math.h文件，进行调整

- 以AS4.3版本为例：
- 将AS4.3安装目录下`\AS43\AS\gnuinst\V4.1.2\i386-elf\include\math.h`中被屏蔽的两段内容解除屏蔽即可。

## 3.2 解决方式二：更改使用函数或指向自定义的头文件函数

# 4 更新日志

| 日期                             | 修改人 | 修改内容 |
| :----------------------------- | :-- | :--- |
| 2024-07-01 | YZY | 初次创建 |
