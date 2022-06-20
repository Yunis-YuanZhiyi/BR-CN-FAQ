# mapp View 中如何设置中文输入
## 问题描述
在mapp View 画面中，如何设置中文键盘拼音输入？ 如何实现中英文输入切换？


## 解决方案

1.在Project.language 中添加中文（注意，这里必须只能选择zh，不能选择其他的zh-CN之类的语言）

![Img](./FILES/020mapp%20View%20中如何设置中文输入.md/img-20220620093106.png)

2.在configuration view中添加TC.textconfig，并对齐进行配置（注意，这里System language或者Fallback language两者必须有一个是zh，下载过后必须重启才能生效）

![Img](./FILES/020mapp%20View%20中如何设置中文输入.md/img-20220620093117.png)

3.mapp View的界面上，你会看到弹出键盘会根据你的当前语言，产生变化，如下图，当语言设置为中文是，键盘如下。左下角可以切换拼音和英文两种输入。
   
![Img](./FILES/020mapp%20View%20中如何设置中文输入.md/img-20220620093219.png)
![Img](./FILES/020mapp%20View%20中如何设置中文输入.md/img-20220620093228.png)

当前语言为英文是，键盘则是下面的样子

![Img](./FILES/020mapp%20View%20中如何设置中文输入.md/img-20220620093233.png)
