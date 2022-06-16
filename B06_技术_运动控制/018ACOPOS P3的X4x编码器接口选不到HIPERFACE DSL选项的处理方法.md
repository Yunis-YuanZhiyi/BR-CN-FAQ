# 018ACOPOS P3的X4x编码器接口选不到HIPERFACE DSL选项的处理方法
## 问题
- ACOPOS P3（8EI8X8HWT10.xxxx-1），在config表中对X4x编码器接口进行配置时，选不到HIPERFACE DSL选项，如下图，如何解决？
- ![Img](./FILES/018ACOPOS%20P3的X4x编码器接口选不到HIPERFACE%20DSL选项的处理方法.md/img-20220616111709.png)

## 解决方式
- 8EI8X8HWT10.xxxx-1支持HIPERFACE DSL类型的编码器，无法在配置表中配置是因为固件版本过低的缘故，请将HW固件版本升级到2.2版本或以上即可。