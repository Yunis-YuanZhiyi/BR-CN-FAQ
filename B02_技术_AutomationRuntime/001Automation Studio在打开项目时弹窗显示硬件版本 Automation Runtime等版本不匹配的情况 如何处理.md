> Tags: #AS #硬件版本

# B02.001.Automation Studio（AS）在打开项目时，弹窗显示硬件版本、Automation Runtime等版本不匹配的情况，如何处理？

- 出现此情况时，是由于AS打开项目时，检测到项目中硬件版本信息，AR版本信息在AS中没有找到对应的文件，不建议点击”Ignore Mismatch“，
- 这将会强行忽视硬件和Automation Runtime版本的差异，在后续对项目进行编译时可能会导致报错。

# 解决办法

- 依照弹窗中显示所需的硬件和Automation Runtime版本进行更新即可。根据自己的AS授权选择相应的更新方式（参考问题7.1）。
- 更新完Automation Runtime、Mapp的版本后，需要手动进行修改。
- ![Img](./FILES/001Automation%20Studio（AS）在打开项目时，弹窗显示硬件版本、Automation%20Runtime等版本不匹配的情况，如何处理？.md/img-20220530003300.png)
