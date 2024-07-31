> Tags: #POWERLINK

- [1 B08.037.如何配置PLC之间的iCN POWERLINK通信](#_1-b08037%E5%A6%82%E4%BD%95%E9%85%8D%E7%BD%AEplc%E4%B9%8B%E9%97%B4%E7%9A%84icn-powerlink%E9%80%9A%E4%BF%A1)
- [2 解决方案](#_2-%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88)
- [3 iCN 的配置](#_3-icn-%E7%9A%84%E9%85%8D%E7%BD%AE)
- [4 主站 MN 的配置](#_4-%E4%B8%BB%E7%AB%99-mn-%E7%9A%84%E9%85%8D%E7%BD%AE)

# 1 B08.037.如何配置PLC之间的iCN POWERLINK通信

# 2 解决方案

- 配置两台PLC之间的POWERLINK通信，需要在同一个项目里进行配置，分配配置两个configuration

# 3 iCN 的配置

- 新建一个Configuration，选择合适的PLC（其中Config1为主站的PLC配置，新建iCN为从站PLC的配置）
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230314135853462.png)
- 在PLK的Configuration中，把站点选成controlled node从站，并配置Cycle time和主站的一致。在Channel出配置需要的输入输出通道，并配置合适的NodeID
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526131542293.png)
- 配置一个输入，一个输出通道
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526132223492.png)

# 4 主站 MN 的配置

- 切换成主站的Configuration：
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230314135913124.png)
- 选择PLK接口，在Toolbox里添加一个iCN站点
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230314135918800.png)
- 右键主站的PLK选择Configuration，设置与从站相同的循环周期2000us
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526131822200.png)
- 右键添加进来的icn站点选择configuration，在Referenced station里选择配置好的站点
    - 现在可以将配置选择出来，这样就对应了刚才的configuration
    - 如果查看icn的io mapping，即可配置之前设置好的输入输出通道，进行POWERLINK数据通信
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526132006351.png)
- 切换到Logical View
    - 在右侧的Toolbox里添加一个程序，新建两个变量用于测试
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526142238881.png)
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526141802981.png)
- 在程序里添加自加的程序，每个周期变量累加1
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526141852719.png)
- 配置主站的数据点
    - 右键epl_icn选择i/o mapping
    - 我们配置主站发送给从站CN的数据点
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526141733046.png)
- 配置从站的数据点
    - 切换到CN的configuration
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526141930321.png)
- 右键PLK选择i/o mapping
    - 添加从站CN发送给主站的数据点
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526141955384.png)
- 监控主站，我们可以看到收到了从站的数据
    - ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526141708172.png)
- 监控 CN 从站，我们可以看到从站也收到了主站的数据
