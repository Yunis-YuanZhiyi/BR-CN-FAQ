## 原因
- 根据掉电保持变量的实际使用量来配置RemMem，不要直接使用最大值。

## 解决方式
- 从Logger看到有此报错，处理建议是减小UserRAM和RemMem的配置量，与实际所需相符。
- 将RemMem size的缺省值15104（最大值）修改为10240（需要的用量）。
- ![](FILES/26263%20AR-DdNV%20Memory%20initialized/image-20230423174959692.png)

