视频网址：

https://www.br-automation.com/zh/academy/knowledge-resource-search/mapp-view-mapp-services-release-information-v516-focus-on-keyboard-operation-and-integrating-the-audit-into-a-report-claby-1629976529104/?noredirect=1

mappServices - 新功能概览

![](file:///C:/Users/pa2j/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

1.      将审计跟踪整合到了mapp Reports中

在5.15的更新中，mapp Reports整合了mapp AlarmX；而在5.16的更新中，则又整合了mapp Audit。这意味着，在5.16版本的mapp Reports中可以将审计也转换成PDF并整合倒输出的Report当中，大大强化了mapp生态圈。

2.      通过mapp AlarmX的异步报警设置，对于时间不那么紧迫的报警性能获得了提升。

3.      在mapp Backup中有了更多的审计事件。

mappServices – 带有mappAudit和mappAlarmX History的mappReport

![](file:///C:/Users/pa2j/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

详细操作请参见视频

为了更好的演示该功能，演讲者制作了一个小应用，分别有报告（Report）、报警历史（Alarm History）和审计轨迹（Audit trail）三个小窗口，开始时为空。演讲者首先在设置温度（Set Temperature）窗口键入了不同数字以创建了若干个事件；而后，他又点击设置报警按钮（Set Alarm Hot / Cold）来添加若干个报警。随后，演讲者点击了创建报告（Create Report）按钮，于是在报告窗口生成了一个.pdf文件；双击之后，可以在左侧的PDF控件中查看所生成的该报告的详细内容。

该报告含有了所有的生成的报警历史和审计轨迹，并且可以通过配置来选择要在报告中显示或隐去哪些项目。

![](file:///C:/Users/pa2j/AppData/Local/Temp/msohtmlclip1/01/clip_image006.jpg)

接下来，演讲者演示了如何在Automation Studio中配置上述功能。首先点击打开mappReport的配置，在MpReport目录下找到Components条目；其中就包含了AlarmHistory和AuditTrail项目。在AuditTrail项目下，可以更改该审计轨迹的名称、Audit trail link以及最大输入数等相关信息；还可以通过SELECT和WHERE这两个项目，对报告的内容和形式进行设置。

mappServices - 表现更好的非同步报警

![](file:///C:/Users/pa2j/AppData/Local/Temp/msohtmlclip1/01/clip_image008.png)

有两种方法可以在Automation Studio中设置报警，分别是配置法和应用法。

配置法:

l   报警被配置到了mapp的配置文件中

l   功能块MpAlarmXCore会基于配置自动地监控与触发报警

优势：不需要写代码

劣势：通常不适用于时间紧迫的报警

应用法：

l   报警被配置到了mapp的配置文件中

l   报警需要通过代码“手动”触发

优势：可以更加自由的编写出发条件

         适用于时间紧迫的报警

劣势：需要写代码

         会占用很多资源

![](file:///C:/Users/pa2j/AppData/Local/Temp/msohtmlclip1/01/clip_image010.png)

关于应用法占用资源的问题

原因：当报警设置好以后，一切都会被执行

l   报警信息被加载

l   时间戳被记录

l   程序片段

l   响应

在同一个循环中设置多个高优先级的报警会导致性能问题

解决方法：异步报警

1.      将报警设置为异步报警

l   只有时间戳会被保存在被调用的任务中

l   报警信息、程序片段和响应的处理会在MpAlarmXcore功能块被调用的任务中进行

l   不适用于时间紧迫的报警

l   十倍性能表现

2.      使用新功能块MpAlarmXAlarmControl（可选）

l   报警信息已经在功能块的内存中加载好了

l   百倍性能表现

l   如果需要，功能块也可以用于非异步报警

可以在mappAlarmX的配置页面下的Behavior下将Asynchronous条目设为True来激活异步报警功能。

mappView – 支持引用本地文件

![](file:///C:/Users/pa2j/AppData/Local/Temp/msohtmlclip1/01/clip_image012.png)

该功能允许使用者在开发mappView可视化时，可以使用不在项目文件夹中的本地文件。也就是说用于mappView可视化开发的资源，可以被存储在项目文件夹外的其他位置。当开发者修改项目中的内容时，本地文件夹中的资源也会同步被修改。

mappView – 键盘混合操作

![](file:///C:/Users/pa2j/AppData/Local/Temp/msohtmlclip1/01/clip_image014.png)

一种全新的与mappView制作的HMI互动的方式。在此之前，要与mappView中的控件进行互动就只能使用触摸或是鼠标点击的方式。现在，与mappView制作的HMI间的互动可以完全通过键盘来进行。

详细操作过程请参见视频。

在使用HMI时，可以通过键盘按键来选择想要交互的控件，无论是数字输入、下拉菜单、勾选控件还是文本框。激活该操作模式的方法如下图，在.vis文件的配置中添加“<Configuration key = “KeyboardOperation” value = “true”/>”即可。

![](file:///C:/Users/pa2j/AppData/Local/Temp/msohtmlclip1/01/clip_image016.jpg)

为了方便键盘操作，可以给mappView控件进行排序。在content的Properties窗口的中（下图红圈处）可以选择Tab Order Page功能来为控件进行排序。

![](file:///C:/Users/pa2j/AppData/Local/Temp/msohtmlclip1/01/clip_image018.jpg)

在点击Tab Order Page后的排序窗口中，可以在TabStop条目下拖动控件名称来对控件进行排序；不需要使用键盘进行操作的控件，也可以将其拖入No TabStop条目下，则该控件将不再能被键盘操作选中。

![](file:///C:/Users/pa2j/AppData/Local/Temp/msohtmlclip1/01/clip_image020.jpg)

mappView 5.16还提供了键盘操作的类型（Keyboard operation styles），目前有三种，分别是Focus、ElementFocus以及Selection。不同的类型在键盘操作时会为控件提供不同的视觉效果，欢迎大家在.styles文件中自行尝试设置不同的类型时会有何种效果。目前大部分控件都支持这些功能，开发团队接下来会努力使支持这些功能的控件越来越多，直至所有控件都支持这些功能。

![](file:///C:/Users/pa2j/AppData/Local/Temp/msohtmlclip1/01/clip_image022.jpg)

问答记录

1.      Q: Does it make sense to use MpAlarmXSet() with a synchronous alarm if the asynchronous one has 10x performance?

A: Yes. If the application requires really fast reaction to the alarm (for instance, doing

something a line after the code has been set), synchronous alarms are still needed.

Q：如果异步报警具有10倍的性能，那么将MpAlarmXSet（）与同步报警一起使用还有意义吗？

A：是的，如果应用程序需要对报警做出快速反应（例如，在设置代码后执行某行操作），则仍然需要设置同步报警。

2.      Q: Is there one instance of MpAlarmXAlarmControl needed per Alarm or can one instance handle more than one?

A: The FUB gets the information about the alarm on the enable. This means that you

can use an instance of the FUB for each alarm, or play from the application to restart

the enable with a new name (this actually removed the performance improvements,

as you will be loading constantly different information for new alarms).

Q：每个报警是否都需要一个MpAlarmXAlarmControl实例，或者一个实例可以处理多个报警？

A：功能块（FUB）获取有关启用报警的信息。这意味着您可以为每个报警使用FUB实例，或从应用程序中播放以使用新名称将其重新启用（这实际上消除了性能改进，因为您将不断为新报警加载不同的信息）。

3.      Q: does the alarmcontrol consume more memory?

A: Yes. It saves the alarm information internally, which will need some memory. The

extra consumption of memory is similar to the memory needed for the monitoring

method.

Q：报警控制是否会消耗更多内存？

A：是的，它会在内部保存报警信息，这需要一些内存。额外消耗的内存量与监控（monitoring）所需的内存量类似。

4.     Q: Is the order of the widget predefined (content editor?) or will it be ordered from top left to bottom right?

A: The navigation order of the widgets can be configured using TabIndex or the

graphical tabStop configurator.

Q：小部件的顺序是否已经预定义（例如在内容编辑器，content editor中）？还是按照从左上到右下的顺序？

A：可以使用TabIndex或tabStop图形配置器来配置小部件的导航顺序。

5.     Q: Does the keyboard tabulation also work within a table list widget to navigate between the cells?

A: Not in 5.16. We will be increasing the widgets supported in each version. Please

look into AS Help for the complete list of currently supported widgets: dadf5b2e-

065a-4ed1-ae76-838ea060b710.

Q：键盘制表功能是否也能用于在表格列表小部件的单元格之间导航？

A：在5.16中还不可以，我们会增加每个版本中支持的小部件。

请查看AS帮助以获取当前支持的小部件的完整列表：

dadf5b2e-065a-4ed1-ae76-838ea060b710。

6.     Q: Is the filemanager widget, or the recipe widget, planned for a specific release?

A: It is currently not planned.

Q：mappView的文件管理器小部件或配方小部件是否计划于特定版本发布？

A：目前还没有该计划

7.      Q: How is the tab stop order determined by default? Is it in the order which widgets were added to the HMI?

A: The whole explanation about how the order is defined can be found in AS Help:

08df769e-5c99-4fec-9103-8c7d2d1c9359.

Q：在默认情况下是如何确定制表位的停止顺序的？是按照添加到HMI的顺序排列吗？

A：关于如何确定顺序的完整解说，请参见AS帮助：

08df769e-5c99-4ec-9103-8c7d2d1c9359。

8.     Q: Are there plans to define a PV for the report name?

A: Currently not planned.

Q：现在是否有计划为报告名称定义一个局部变量？

A：目前还没有该计划。