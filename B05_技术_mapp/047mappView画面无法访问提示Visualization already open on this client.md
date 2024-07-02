> Tags: #mappView

- [1 B05.047-mappView画面无法访问提示Visualization already open on this client](#_1-b05047-mappview%E7%94%BB%E9%9D%A2%E6%97%A0%E6%B3%95%E8%AE%BF%E9%97%AE%E6%8F%90%E7%A4%BAvisualization-already-open-on-this-client)
- [2 原因一：配置中Maximal client connections 太小](#_2-%E5%8E%9F%E5%9B%A0%E4%B8%80%EF%BC%9A%E9%85%8D%E7%BD%AE%E4%B8%ADmaximal-client-connections-%E5%A4%AA%E5%B0%8F)
- [3 原因二：在一个项目中同时配置了mappSafety与mappView](#_3-%E5%8E%9F%E5%9B%A0%E4%BA%8C%EF%BC%9A%E5%9C%A8%E4%B8%80%E4%B8%AA%E9%A1%B9%E7%9B%AE%E4%B8%AD%E5%90%8C%E6%97%B6%E9%85%8D%E7%BD%AE%E4%BA%86mappsafety%E4%B8%8Emappview)
- [4 原因三：在一个项目中同时配置了mappVison与mappView](#_4-%E5%8E%9F%E5%9B%A0%E4%B8%89%EF%BC%9A%E5%9C%A8%E4%B8%80%E4%B8%AA%E9%A1%B9%E7%9B%AE%E4%B8%AD%E5%90%8C%E6%97%B6%E9%85%8D%E7%BD%AE%E4%BA%86mappvison%E4%B8%8Emappview)
- [5 原因四：对时服务未开启，系统时间存在跳变](#_5-%E5%8E%9F%E5%9B%A0%E5%9B%9B%EF%BC%9A%E5%AF%B9%E6%97%B6%E6%9C%8D%E5%8A%A1%E6%9C%AA%E5%BC%80%E5%90%AF%EF%BC%8C%E7%B3%BB%E7%BB%9F%E6%97%B6%E9%97%B4%E5%AD%98%E5%9C%A8%E8%B7%B3%E5%8F%98)
- [6 更新日志](#_6-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 B05.047-mappView画面无法访问提示Visualization already open on this client

- 使用浏览器访问mappView画面，提示Visualization already open on this client, no further sessions allowed。
    - ![](FILES/047mappView画面无法访问提示Visualization%20already%20open%20on%20this%20client/image-20240702113158218.png)

# 2 原因一：配置中Maximal client connections 太小

- 项目 Configuration View → Config.mappviewcfg → Maximal client connections 设置的参数太小
    - ![](FILES/047mappView画面无法访问提示Visualization%20already%20open%20on%20this%20client/image-20240702130136664.png)
- 例如设置了允许最大客户端连接数量为 1 ，而同时有 2 个客户端访问mappView画面，则第 2 个客户端会提示报错
    - ![](FILES/047mappView画面无法访问提示Visualization%20already%20open%20on%20this%20client/image-20240702130157547.png)

# 3 原因二：在一个项目中同时配置了mappSafety与mappView

- 现象
    - 如果一个项目中同时有 mappSafety 画面与mappView画面，则无法直接访问 mappSafety 独立的网页画面也无法使用 WebViewer 部件来尝试切换页面
    - MappView 和 mappSafety 画面无法再同一个AR上同时使用
    - ![](FILES/047mappView画面无法访问提示Visualization%20already%20open%20on%20this%20client/image-20240702130959985.png)
- 规避方式
    - 将mappSafety的画面集成至mappView画面中
    - ![](FILES/047mappView画面无法访问提示Visualization%20already%20open%20on%20this%20client/image-20240702131843862.png)
- 对应帮助信息
    - GUID: c4615df7-7044-4151-bbb5-4592c6c31810
    - [在线英文帮助链接 B&R Online Help (br-automation.com)](https://help.br-automation.com/#/en/4/visualization%2Fmappview%2Fengineering%2Flv_page%2Flv_page_area.html)

# 4 原因三：在一个项目中同时配置了mappVison与mappView

- 原因与解决方式同原因二
- ![](FILES/047mappView画面无法访问提示Visualization%20already%20open%20on%20this%20client/image-20240702133921834.png)

# 5 原因四：对时服务未开启，系统时间存在跳变

- 建议开启NTP对时服务，确保AR的时间，浏览器所在操作系统的时间是正确的
- 若使用Hypervisor，建议设置 Hypervisor 跟 Windows系统的时间同步
- 升级AR至 2021-04-15（D4.90） 及之后发布的AR版本（影响范围 4.7 ~ 4.11 的AR ）
    - 开始出现此BUG的版本：B4.73
    - 建议使用此AR版本及之后版本：
        - D4.73
        - C4.83
        - D4.90
        - B4.91
        - A4.92
    - 检查Logger，可能会见到30993报错

# 6 更新日志

| 日期         | 修改人                     | 修改内容 |
| :--------- | :---------------------- | :--- |
| 2024-07-02 | HQ<br>YZY<br>WKJ<br>DYC | 初次创建 |
