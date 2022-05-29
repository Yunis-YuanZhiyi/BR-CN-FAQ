# 005通过调用PVI的函数实现和贝加莱控制器通信时，上位程序执行写变量函数WriteValue后，返回值为0指的是数据已经写到PLC的内存？还是指变量已经发送给PVI Manager，需要等待一段时间PVI Manager才能写给PLC？
Tags：PVI、通信
A： 
返回值为0表示已经传到了PVI Manager，指的是可以在进行一次写操作。