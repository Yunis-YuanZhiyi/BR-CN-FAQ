> Tags: #AR

# B02.003.如何知道当前控制器中Automation Runtime （AR）的版本？

- <span style="background:#A0CCF6">1___</span>通过ETH接口将控制器与电脑相连，进入Automation Studio建立控制器与电脑之间的连接。
- <span style="background:#A0CCF6">2___</span>新建一个工程，点击Transfer按钮，空白工程编译完成后会跳出下载界面。
- <span style="background:#A0CCF6">3___</span>下载界面左上方的AR Version表示当前项目在Automation Studio中选择的AR版本
- <span style="background:#A0CCF6">4___</span>下载界面右上方的AR Version表示当前控制器中的AR版本
    - ![Img](./FILES/003如何知道当前控制器中Automation%20Runtime%20（AR）的版本？.md/img-20220530003422.png)
- 请注意，点击Transfer将程序下载至控制器后，控制器的AR版本会替换成当前项目在Automation Studio中选择的AR版本。
- 如果想要更换当前项目在Automation Studio中选择的AR版本，则需要点击最上方浮标栏的Project→Change Runtime Versions→Automation Runtime，进行相应版本的选择。
