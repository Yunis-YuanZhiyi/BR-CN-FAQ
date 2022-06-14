# 004在mappView中给按钮绑定变量时，确定键为灰色，无法进行绑定？
Tags：mappView、绑定变量

A：
	检查是否添加binding文件，如果bindings set id条目中为空则说明binding文件未添加
	检查按钮是否支持绑定该类型的变量
