# 001Automation Studio（AS）梯形图LD编辑环境中如何调用函数库？
Tags：梯形图、LD、库

A：

贝加莱的函数分成两种形式的，不同形式的函数，调用方式如下：
1）唯一返回值的函数，直接添加普通block，直接写函数即可。
2）FB类的库，先添加库，再建立函数的变量。然后添加FB，并输入建立好的变量。