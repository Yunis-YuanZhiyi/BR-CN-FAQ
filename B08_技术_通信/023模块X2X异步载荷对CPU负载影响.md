# 023模块X2X异步载荷对CPU负载影响

## 问题

![Img](./FILES/023X2X异步载荷对CPU负载影响.md/img-20220623110653.png)

- 修改这个X2X 的异步负载大小对CPU的负载有影响吗？

## 回答

- X2 X 的异步是用来更新 IO 固件，读写异步寄存器用的，对 CPU 没啥影响，对 IO 点数会有影响。
