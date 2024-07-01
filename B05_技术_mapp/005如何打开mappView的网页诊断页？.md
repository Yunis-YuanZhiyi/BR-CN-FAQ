> Tags: #mappView #诊断分析
- [1 B05.005-如何打开mappView的网页诊断页？](#_1-b05005-%E5%A6%82%E4%BD%95%E6%89%93%E5%BC%80mappview%E7%9A%84%E7%BD%91%E9%A1%B5%E8%AF%8A%E6%96%AD%E9%A1%B5%EF%BC%9F)
- [2 配置方式](#_2-%E9%85%8D%E7%BD%AE%E6%96%B9%E5%BC%8F)
- [3 访问方式](#_3-%E8%AE%BF%E9%97%AE%E6%96%B9%E5%BC%8F)

# 1 B05.005-如何打开mappView的网页诊断页？

# 2 配置方式

- 首先需要在AS项目ConfigurationView中打开mappView文件夹中的Config.mappView配置文件
    - ![Img](./FILES/005如何打开mappView的网页诊断页？.md/img-20220530215926.png)
- 在配置界面中打开高级属性（Change Advanced Parameter Visibility）
    - ![Img](./FILES/005如何打开mappView的网页诊断页？.md/img-20220530220135.png)
- 找到Diagnostic Configuration条目并进行适当配置即可
    - ![Img](./FILES/005如何打开mappView的网页诊断页？.md/img-20220530220250.png)
- 配置完成后编译下载程序

# 3 访问方式

- 在浏览器地址栏中输入 http://IP地址:81/server/info 后，正确输入项目中设定的管理员用户名和密码即可登录mappView的网页诊断页。
- 注意，在使用ARSim进行仿真时，默认的IP地址为127.0.0.1，此时诊断页的地址为 http://127.0.0.1:81/server/info ，如下图所示：
- ![Img](./FILES/005如何打开mappView的网页诊断页？.md/img-20220530004604.png)
