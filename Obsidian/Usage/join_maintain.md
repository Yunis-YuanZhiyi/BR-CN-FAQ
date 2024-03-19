- [1 加入我们，一起维护🎉](#_1-%E5%8A%A0%E5%85%A5%E6%88%91%E4%BB%AC%EF%BC%8C%E4%B8%80%E8%B5%B7%E7%BB%B4%E6%8A%A4)
- [2 维护方式](#_2-%E7%BB%B4%E6%8A%A4%E6%96%B9%E5%BC%8F)
	- [2.1 如何创建文件](#_21-%E5%A6%82%E4%BD%95%E5%88%9B%E5%BB%BA%E6%96%87%E4%BB%B6)
	- [2.2 如何搜索](#_22-%E5%A6%82%E4%BD%95%E6%90%9C%E7%B4%A2)
- [3 维护思路](#_3-%E7%BB%B4%E6%8A%A4%E6%80%9D%E8%B7%AF)
- [4 维护规则](#_4-%E7%BB%B4%E6%8A%A4%E8%A7%84%E5%88%99)
	- [4.1 附件下载添加规则](#_41-%E9%99%84%E4%BB%B6%E4%B8%8B%E8%BD%BD%E6%B7%BB%E5%8A%A0%E8%A7%84%E5%88%99)
	- [4.2 视频显示规则](#_42-%E8%A7%86%E9%A2%91%E6%98%BE%E7%A4%BA%E8%A7%84%E5%88%99)

# 1 加入我们，一起维护🎉

# 2 维护方式

- [Gitee](https://gitee.com/yzydeer/BuR-FAQ)
- [Github](https://github.com/Yunis-YuanZhiyi/BR-CN-FAQ)
- [Bitbucket 内部维护](https://bitbucket.br-automation.com/projects/FIWW/repos/faq/browse)

## 2.1 如何创建文件

- [使用模版创建文件方式](使用模版创建文件方式.md)

## 2.2 如何搜索

- [如何搜索帮助](/C01_其他/007如何搜索帮助.md)

# 3 维护思路

- 使用obsidian软件编写markdown文本
    - 通过插件配合调整文档内容
- 使用docsify发布至腾讯云服务器
    - 通过docsify插件实现相关功能
- 域名解析至 brhelp.cn 网站

# 4 维护规则

- 编写markdown软件
    - Obsidian
        - [Obsidian - Sharpen your thinking](https://obsidian.md/)
    - 对应使用FAQ定制配置文件
        - [点击跳转下载](https://www.br-education.com/downloadDis/72)
- 创建条目标题命名规则
    - 按照分类建立条目，一个问题一个条目，尽量用少量字数描述
    - 已创建的文件名，如无必要，不要改名
    - 条目开头均以 0XX 三位数字开头，方便定位
    - 条目标题末尾不能有多余空格，不能以 `.`，`?` 结尾
    - 条目标题中不能包含 `%`，`'` 与 `"`
- 图片使用
    - 图片尽量使用 `pixpin` 软件截图，减少图片占用体积
        - [PixPin 截图/贴图/长截图/文字识别/标注 | PixPin 截图/贴图/长截图/文字识别/标注 (pixpinapp.com)](https://pixpinapp.com/)
    - 图片体积控制在 300KB 以下
    - 尽量确保图片小，不要有过多留白，尽量突出重点，方便手机浏览
- 动图使用
    - 使用 `ScreenToGif` 软件制作 Gif 动图，并进行压缩，控制体积
        - [ScreenToGif - Record your screen, edit and save as a gif, video or other formats](https://www.screentogif.com/)
- 文本内容
    - 开头内容以 `> Tags: #标签` 方便后续归类
    - 第一个 H1 样式的内容为 A01.001-标题名，方便查询
    - 文内 H1 H2 H3 等标题样式，尽量简洁，不要有以标点符号结尾，避免目录生成不跳转
    - 文中内容以列表的方式进行编写，便于格式统一
    - 不要导入 WORD 文件，请使用 `Writage` 转换为 Markdown 文件
        - [Writage - Markdown plugin for Microsoft Word](https://www.writage.com/)
- 附件与视频上传
    - 无必要不上传视频，若为了演示，建议使用 `Handbrake` 软件将视频进行压缩在1MB以内
        - [HandBrake: Open Source Video Transcoder](https://handbrake.fr/)
    - PDF若大于5MB，建议放在网盘或者下载中心，使用链接指向。
    - 项目压缩包，建议压缩在5MB以内上传
- 无效资源清空
    - 避免无效资源被推送
    - 新写的内容，右键文件夹，选择 `Find orphaned files` 将提示出没有任何关联的文档且无效的资源删除
    - 确认完成后删除在根目录下的 Find orphaned files 输出文件

## 4.1 附件下载添加规则

- 绝对路径
- 链接末尾添加 ':ignore'

```
[通用功能 | BrRand库，动态生成随机数 | 2021-09-24](/B04_技术_贝加莱功能库Library/FILES/000B04_技术_贝加莱功能块Library/BrRand-2021-09-24.zip ':ignore')
```

## 4.2 视频显示规则

- 绝对路径
- 使用HTML语法实现

```
<video muted autoplay="autoplay" loop="loop" width="320" height="240" controls>
  <source src="/A06_产品_柔性传输系统/FILES/003ACOPOS_6D是什么/1.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
```
