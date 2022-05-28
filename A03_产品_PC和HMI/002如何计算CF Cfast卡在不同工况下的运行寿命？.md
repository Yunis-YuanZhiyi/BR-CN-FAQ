# 002如何计算CF Cfast卡在不同工况下的运行寿命？
Tags：存储卡、寿命；
A： 
方法一：
使用ArStorage库获取存储介质寿命情况。
注1：参见Automation Studio帮助 Guid ID：15e55f50-8140-49b8-b7c0-8c6ea1dc8a65。
注2：该库仅针对SG4的系统，AR 需在V4.90或更高版本中使用。

方法二： 
对于具有S.M.A.R.T功能的CF/Cfast卡可通过SBLTM软件获取CF卡运行1个周期的AEC差值，再根据CF/Cfast卡的Clear/Write cycles值，
从而计算出CF/Cfast卡大致运行寿命：
1)	通过s.m.a.r.t读取数据存储介质的“平均擦除计数”
2)	在规定的一段时间内(如1周)，用相关的数据存储介质完全操作系统。
3)	通过“平均擦除计数”确定使用的擦除周期。
4)	根据最大保证写/擦除周期(MLC： 3000, SLC： 100,000)确定预期的使用寿命。
5)	SBLTM软件不是贝加莱官方软件，如有需要请联系技术支持部

注1：CF卡的S.M.A.R.T数值只能通过具有CF卡槽与硬盘卡槽的贝加莱工控机读取。Cfast卡的S.M.A.R.T数据可通过普通电脑获取。
注2：参见Automation Studio帮助 Guid ID：6c5d0a49-0468-4100-91c0-f30712abd55a；
