请由下及上参阅（方便笔者书写与调试）
=
***
## sublime3下实现Markdown的实时自动刷新预览（Markdown Preveiw+LiveReload）
* Ctrl+Shift+p（调用命令面板）、输入PCIP（Package Control:Install Package）回车、输入MP（Markdowm Preview），下载并安装
* Markdown Preview默认没有快捷键，我们可以为其设置快捷键  
        1. Preferences -> Key Bindings打开的文件的右侧栏的中括号中添加一行代码    
```
{ "keys": ["alt+m"], "command": "markdown_preview", "args": {"target": "browser", "parser":"markdown"}  }
```  
      2. 打开其配置文件 Preferences -> Package Settings -> Markdown Preview -> Settings，检查左侧enable_autoreload
      条目是否为true，若是，跳过。若不是，右侧栏加一条下面这个后重启Sublime:
```
{
    "enable_autoreload": true
}
```
* 安装并配置LiveReload  
       1. Ctrl+Shift+p（调用命令面板）、输入PCIP（Package Control:Install Package）回车、输入LiveReload，下载并安装  
      2. 安装成功后, 再次Ctrl+shift+p, 输入LiveReload: Enable/disable plug-ins, 回车, 选择 Simple Reload with 
         delay (400ms)或者Simple Reload，两者的区别仅仅在于后者没有延迟。  
      3.  安装完毕重启sublime3，新建一个.md文件测试，快捷键Alt+m,调出浏览器预览
*  __注意：__ 每次重启后发现不能够实时刷新了，需要重新ctrl + shift + p 找到 livereload 重新选择 加载 !!!
## 表格
> arkdown 制作表格使用 | 来分隔不同的单元格，使用 - 来分隔表头和其他行。
> 1. -: 设置内容和标题栏居右对齐。
> 2. :- 设置内容和标题栏居左对齐
> 3. :-: 设置内容和标题栏居中对齐。  

表头| 表头| 表头| 表头| 表头 
:-|:-:|-:|:-|:-:
左对齐|中对齐|右对齐|左对齐|中对齐
左对齐|中对齐|右对齐|左对齐|中对齐
左对齐|中对齐|右对齐|左对齐|中对齐
左对齐|中对齐|右对齐|左对齐|中对齐
左对齐|中对齐|右对齐|左对齐|中对齐

## 高级链接（变量赋值前一定要加空行）
链接到 [cnode][1]  
链接到 [w3school][2]  

[1]: https://cnodejs.org    
[2]: https://www.w3school.com.cn    
## 代码
1. 代码片段（反引号包围``）    
`console.log('test')`
2. 代码区块（前加四个空格或三个反引号包裹）   
function test(){    
    console.log('abc')  
    }
3. javascript
```javascript
function test(){    
console.log('abc')  
}   
```

## 脚注（无法实现）
[^脚注]:我们总以为，是生活欠我们一个“满意”，其实是我们欠生活一个“努力”。
## 下划线（无法实现）
<u>带下划线</u>  
## 删除线
~永远不要沉溺在安逸里得过且过，能给你遮风挡雨的，同样能让你不见天日，只有让自己更加强大，才能真正撑起一片天。~
## 分隔线（三个及以上的星、减号、底线）
***  
---  
___
## 字体
**粗体**  
__粗体__  
*斜体*  
_斜体_  
***粗体斜体***  
___粗体斜体___  
## 粗体与斜体
你的*对手*在看书，你的*仇人*在磨刀，你的*闺蜜*在减肥，隔壁*老王*在练腰，你必须不断地**努力**，才能不让你的对手有可乘之机。
## 引用
> 若不努力,除了年纪在涨,头发变少,容颜变老,你买不起的还是买不起,你喜欢的人还是与你无关...  
## 引用（换行用回车或句子后面加两个空格）
> 天行健，  
> 君子以自强不息

> 地势坤，

> 君子以厚德载物
## 区块嵌套
> 最外层  
>> 第一层  
>>> 第二层
## 区块中使用列表
> 区块
> 1. 第一项
> 2. 第二项
> 3. 第三项
## 列表中使用区块
* 第一项
    >你好吗  
    >你好吗  
    >你好吗  
 * 第二项
## 插入图片或链接  
    ![alt 属性文本](图片地址 "可选标题")或者也可以像高级链接那样使用
 
[github](https://github.com)    
![Cnode UserAvatar](https://avatars2.githubusercontent.com/u/14975630?v=4&s=120 'Cnode UserAvatar')  
>  高级链接模板
>> 链接到[github][1]  
>> 链接到[cnode userAvatar][2]

[1]: https://github.com 
[2]: https://avatars2.githubusercontent.com/u/14975630?v=4&s=120
## 无序列表（可以是星号、加号、减号）
* 列表一
* 列表一
* 列表一

+ 列表一
+ 列表一
+ 列表一

- 列表一
- 列表一
- 列表一
## 有序列表
1. 列表一
2. 列表一
3. 列表一
## 列表嵌套（在字列表的前面加四个空格）
1. 第一项
    + 列表一 
    + 列表一 
    + 列表一 
    + 列表一 
2. 第二项
- 列表一 
    - 列表一  
    - 列表一 
    - 列表一 
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
我是一级标题
======
我是二级标题
-
