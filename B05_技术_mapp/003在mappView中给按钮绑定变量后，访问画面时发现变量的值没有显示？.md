> Tags: #mappView 
# B05.003-在mappView中给按钮绑定变量后，访问画面时发现变量的值没有显示？

- 这是由于项目中没有引用binding文件所导致的。
- 进入Configuration View的MappView文件夹，双击打开Visualizat.vis文件中，检查BindingSets条目下是否写入了refID。
- 确保该ID与.binding文件中的refID一致。重新下载后，进入画面即可。