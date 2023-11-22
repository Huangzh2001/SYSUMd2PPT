如何快速生成组会PPT

## 工具的安装

- 在VsCode中安装插件:"Marp for VS Code"

## 模板的使用

- 将项目中的下面三个文件与你要转化为PPT的Markdown文件放在同一个文件夹
  
  - .vscode
    
  - images
    
  - themes
    
- 然后在你的Markdown文件开头加上
  
  ```markdown
  ---
  marp: true
  theme: SYSUPPT
  paginate: false % 如果想要添加页面编号,则将这个值设为true
  
  ---
  
  ![bg](./images/SYSU_cover.png) % 如果想要加上封面,则添加这个语句
  
  ---
  
  <!-- backgroundImage: url("./images/SYSU_title.png") -->
  ```
  
- 如果你想要在PPT最后一页加上结尾,则在你的Markdown文件最后面加上
  
  ```markdown
  ![bg](./images/SYSU_thanks.png)
  ```
  
- 我们可以使用三个杠'---'或三个星号来给PPT分页
  
- 如果想要在每页PPT左上角加上标题,比如我们想要增加标题"工作汇报",我们可以在该页PPT中加上如下命令:
  
  ```markdown
  <!-- _header: 工作汇报 -->
  ```
  
- 最后,我们可以通过VsCode右上角与插件"Marp for VS Code"图标相同的按钮将PPT导出

## 其他问题

- 如果我们使用Zotero Better Notes中的模板,那么就会出现`<span>`标签,但marp无法识别这个标签,会出现乱码.我们可以在VsCode中按下快捷键Ctrl+H,然后选择正则表达式替换.搜索下面的正则表达式,将其替换为空格:
	```
	<span[\s\S]*?>
	<a[\s\S]*?>
	</[\s\S]*?>
	```
