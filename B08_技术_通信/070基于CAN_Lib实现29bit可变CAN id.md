> Tags: #CAN

- [1 070基于CAN_Lib实现29bit可变CAN id](#_1-070%E5%9F%BA%E4%BA%8Ecan_lib%E5%AE%9E%E7%8E%B029bit%E5%8F%AF%E5%8F%98can-id)
- [2 原11bit的代码情况](#_2-%E5%8E%9F11bit%E7%9A%84%E4%BB%A3%E7%A0%81%E6%83%85%E5%86%B5)
- [3 解决方式](#_3-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [4 更新日志](#_4-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 070基于CAN_Lib实现29bit可变CAN id

- 使用11bit的固定id，现在改用29bit的可变id，原来程序不再适用。CAN_Lib库是否支持可变id？

# 2 原11bit的代码情况

- 原来是11bit的固定id，使用CANMulQueue()和CANMulrd()，对多个设备进行读写。
- ![](FILES/070基于CAN_Lib实现29bit可变CAN%20id/image-20241205000525923.png)
- ![](FILES/070基于CAN_Lib实现29bit可变CAN%20id/image-20241205000546702.png)
- 现在改用29bit的可变id，id不单单是一个id号，并且包含其它状态信息，当状态发生变化时，id也会发生变化，不再是一个固定id，所以原来的程序读id时会报错读不到。
- ![](FILES/070基于CAN_Lib实现29bit可变CAN%20id/image-20241205000611709.png)

# 3 解决方式

- 使用 CANqueue()，该功能块可以对id进行屏蔽（id使用值：0xFFFFFFFF），读取所有id的数据。
    - 经测试，配合 CANrd() 确实可以读到所有id的数据。但是只读到了数据，无法读到对应的id。
    - ![](FILES/070基于CAN_Lib实现29bit可变CAN%20id/image-20241205000655175.png)
- 使用 CANxrd() 读取数据，该功能块既可以读到数据，也可以返回该数据对应的id。
    - 经测试，CANqueue() 配合 CANxrd() 可以满足29bit可变id的需求。

# 4 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2024-12-05 | MSS | 初次创建 |
