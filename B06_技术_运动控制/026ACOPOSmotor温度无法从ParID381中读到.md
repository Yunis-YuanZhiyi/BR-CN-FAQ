# 现象
- ACOPOSmotor  8DI 电机温度？现在读到ID381MOTOR TEMP都是0。
	- 读取温度参数ID64 ~ ID73都是0，手写了温度参数组ID64 ~ ID73后，ID381也是0。

- 有些项目中，ACOPOSmotor的温度读取是看根据模型算出来的理论温度。
	- 393: Motor: Temperature model: Temperature: TEMP_MOTOR_MODELL
- 由于编码器是Endat 2.2，因此可尝试读编码器的温度来得到实际温度：
	- 895: Encoder1: Temperature
	- ![](FILES/026ACOPOSmotor温度无法从ParID381中读到/image-20221019191212258.png)
# 解决方式
- 读ParID 895
	- ![](FILES/026ACOPOSmotor温度无法从ParID381中读到/image-20221019191247113.png)


