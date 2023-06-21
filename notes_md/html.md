## Web标准：

1. **结构** ：HTML -> 页面元素
2. **表现** ： CSS -> 页面样式
3. **行为** ： JavaScript -> 页面交互的动态效果



## HTML

###### 超文本标记语言（Hyper Text Markup Language）

- 载入内容,包括文本、音频、图片等等

#### <a name= "key" id="key"> Key</a>

###### 注释

- `<!-- 语句注释内容 -->`
- `<comment> 段落注释内容 </comment>`

###### 标题

- `<title>显示在网址栏标题</title>`

###### 注明文件

- `<!DOCTYPE element-name DTD-type DTD-name DTD-urk>`：位于`<html>`标记之前，标记使用的规范类型
- DTD三种类型
  - 严格型：HTML Strict DTD
  - 过渡型：HTML Transitional DTD
  - 框架型：HTML Frameset DTD

- `<!DOCTYPE html>` ：注明文件类型为html

###### 语言

- `<html lang="en">`

- 语言标签，向浏览器指明网页主要使用的语言

  | `lang` | Explaination |
  | :----: | :----------: |
  | zh-CN  |   简体中文   |
  | zh-TW  |   繁体中文   |
  |   en   |     英语     |
  |   ru   |     俄语     |
  |   ja   |     日语     |
  |   fr   |     法语     |

  - 更多编码跳转维基百科[ISO_639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) 

###### 元信息标记

- `<meta name="NAME" content="CONTENT">`

  |    Value    | Explaination |
  | :---------: | :----------: |
  |   author    |   网页作者   |
  | description | 网页简短描述 |
  |  keywords   |  网页关键词  |
  |  generator  |    编辑器    |

  | Attribute |   Value   |              Explaination              |
  | :-------: | :-------: | :------------------------------------: |
  |  content  | some_text | 定义与http-equiv或name属性相关的元信息 |

  ```html
  <meta name = "keywords" content = "CONTENT">
  <!-- 网页关键词 -->
  
  <meta name = "description" content = "CONTENT">
  <!-- 网页简要说明 -->
  
  <meta name = "author" content = "CONTENT">
  <!-- 作者信息 -->
  
  <meta name = "generator" content = "CONTENT">
  <!-- 指明生成页面工具 -->
  
  <meta name = "copyright" content = "CONTENT">
  <!-- 页面版权信息 -->
  
  <meta name = "robots" content = "CONTENT">
  ```

  - robots告诉搜素引擎机器人抓取哪些页面

    |  Value   |                 Explain                  |
    | :------: | :--------------------------------------: |
    |   all    |  文件将被检索，且页面上的链接可以被查询  |
    |   none   | 文件将不被检索，网页上的链接不可以被查询 |
    |  index   |               文件将被检索               |
    | noindex  | 文件将不被检索，但网页上的链接可以被查询 |
    |  follow  |          页面上的链接可以被查询          |
    | nofollow | 文件将被检索，但页面上的链接不可以被查询 |

- `<mata http-equiv>`

- 用于提供http协议的响应头报文
  ```html
  <meta http-equiv = "cache-control " content = "no-cache">
  <!-- 设置限制，仅从服务器获取资源而不是从本地cache中 -->
  <meta http-equiv = "refresh" content = "5; url = http://zachary.world">
  <!-- 5s后重定向到指定的网页 -->
  <meta http-equiv = "content-type" content="text/html;charset=utf-8"/>
  <!-- 指定编码字符集 -->
  <meta http-equiv = "expires" content="Sat, 26 Feb 2022 08:00:00 GMT"/>
  <!-- 指定到期时间 -->
  ```

###### 主体


- 主体样式

  ```html
  <body>
  <!-- 主体内容 -->
  </body>
  ```

- 标记属性

  - 设置body的标记属性可以改变页面的样式

  ```html
  <body leftmargin="50px" topmargin="50px" text="#000000" bgcolor="#339999" link="red" alink="black" vlink="blue" background="../imags/1.jpg">
  ```

  - 属性详情
    
    | Attribute  |                            Value                             |                         Explaination                         |
    | :--------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
    |    text    | <a name="body_attribute">rgb(r,g,b)<br />rgb(r%,g%,b%)<br />#rrggbb或#rgb<br />colorname</a> | rgb函数（Int，取值0～255）<br />rgb函数（percent，取值0～100）<br />十六进制数（6位或3位，0～9，A～F）<br />颜色英文名（red,green,blue etc. ） |
    |  bgcolor   |                             同上                             |                规定文档的背景颜色，不建议使用                |
    |   alink    |                             同上                             |                   规定文档中的活动链接颜色                   |
    |    link    |                             同上                             |                  规定未访问的链接的默认颜色                  |
    |   vlink    |                             同上                             |                   规定已被访问的链接的颜色                   |
    | background |                             URL                              |          规定文档的背景图像（图像过大影响访问速度）          |
    | topmargin  |                            pixel                             |                   规定文档中的上边距的大小                   |
    | leftmargin |                            pixel                             |                    规定文档中左边距的大小                    |



###### 标记类型

- 单标记：单标记元素没有结束标记，通常用于表示没有内容的元素。
- 双标记：双标记元素有开始和结束标记，用于表示包围在标记中的内容。

###### 标签间的关系

父子关系（嵌套关系）

- for example：

	```html
  <head>
  	<title> son </title>
  </head>
	```

- 兄弟关系（并列关系）

  - eg.

    ```html
    <head></head>
    <body></body>
    ```

###### H系列 

—— 即六种标题

- `<h1></h1>`

- `<h2></h2>`

- `<h3></h3>`

- `<h4></h4>`

- `<h5></h5>`

- `<h6></h6>`

###### 段落

- `<p align = center> central paragraph </p>`

###### 换行&水平线

- `<br>` or `<br/>`
- `<hr width="" size="" color="">`

  | Attribute |                    Value                     |  Explaination  |
  | :-------: | :------------------------------------------: | :------------: |
  |   width   |              像素（px）或百分比              | 设置水平线宽度 |
  |   size    |                整数（单位px）                | 设置水平线高度 |
  |   color   | 同<a href="#body_attribute">body属性颜色</a> |    设置颜色    |
  |   align   |           left \| center \| right            |    设置位置    |

###### 文本格式

- 文本位置

  |    key    | Explanation |
  | :-------: | :---------: |
  |  `left`   |   左对齐    |
  | `center`  |    居中     |
  |  `right`  |   右对齐    |
  | `justify` |  两端对齐   |
- 特殊字符

  | Display  | Explaination |    Code    |
  | :------: | :----------: | :--------: |
  |  &nbsp;  | 显示一个空格 |  `&nbsp;`  |
  |   &lt;   |     小于     |   `&lt;`   |
  |   &gt;   |     大于     |   `&gt;`   |
  |  &amp;   |    &符号     |  `&amp;`   |
  |  &quot;  |    双引号    |  `&quot;`  |
  |  &copy;  |     版权     |  `&copy;`  |
  |  &reg;   |   注册商标   |  `&reg;`   |
  | &times;  |     乘号     | `&times;`  |
  | &divide; |     除号     | `&divide;` |
- 拼音格式

  ```html
  <ruby>
    中<rt>
    		zhong
    	</rt>
  	国<rt>
    		guo
    	</rt>
  </ruby>
  ```



- 文本修饰

  | Explaination |        key        |         key         |
  | :----------: | :---------------: | :-----------------: |
  |     加粗     |     `<b></b>`     | `<strong></strong>` |
  |    下划线    |     `<u></u>`     |    `<ins></ins>`    |
  |     倾斜     |     `<i><i>`      |     `<em></em>`     |
  |    删除线    |     `<s></s>`     |    `<del></del>`    |
  |     变大     |   `<big></big>`   |                     |
  |     变小     | `<small></small>` |                     |
  |     上标     |   `<sup></sup>`   |                     |
  |     下标     |   `<sub></sub>`   |                     |
- 引用和术语

  |                 key                  |  Explaination  |
  | :----------------------------------: | :------------: |
  |        `<abbr> etc. </abbr>`         |    定义缩写    |
  | `<address> Beijing China </address>` |    定义地址    |
  | `<blockquote> 长引用 </blockquote>`  |   定义长引用   |
  |     `<cite> 引用、引证 </cite>`      |  定义引用引证  |
  |         `<q> 短语引用 </q>`          |  定义短引用语  |
  |       `<dfn> 定义项目 </dfn>`        | 定义个定义项目 |
- 计算机输出标记

  |             key              |    Explaination    |
  | :--------------------------: | :----------------: |
  |    `<code> code </code>`     |   定义计算机代码   |
  | `<kbd> keyboard code </kbd>` |     定义键盘码     |
  |   `<samp> sample </samp>`    | 定义计算机代码样本 |
  |  `<tt> printer code </tt>`   |   定义打印机代码   |
  |   `<var> variable </var>`    |      定义变量      |
  |   `<pre> pre text </pre>`    |    定义预格式化    |
  
  

###### 字体

- `<font key1="" key2="" ...> ... </>`

- 字体属性标记：

  | Attribute |                    Value                     |                         Explaination                         |
  | :-------: | :------------------------------------------: | :----------------------------------------------------------: |
  |   size    |             +1～+7，1～7，-1～-7             |                       同数值大小相匹配                       |
  |   color   | 同<a href="#body_attribute">body属性颜色</a> |         同<a href="#body_attribute">body属性颜色</a>         |
  |   face    |              字体1,字体2,......              | 可以有多个值，用逗号分隔。从左到右依此选用，都不存在，默认为宋体 |

###### 滚动文字

- 为文字添加滚动的效果，丰富页面内容

  ```html
  <marquee width="" height="" bgcolor="" direction="up|down|left|right" 
           behavior="scoll|slide|alternate" hspace="" vspace="" scollamount="" scolldelay="" 
           loop="" onmouseover="this.stop()" onMouseOut="this.start()">
    <font size="4"> 
    	这是一个滚动的文字
    </font> 
  
  </marquee>
  ```

  - 宽度，高度：width,height
  - 背景色：bgcolor，值同<a href="#body_attribute">body属性颜色</a>
  - 方向：direction 上下左右
  - 表现：behavior平滑，滚动，交替
  - 边距：hspace,vspace
  - 滚动速度、暂停时间：scollamount,scolldelay
  - 循环次数：loop
  - 鼠标悬停停止，离开继续滚动：onmouseover,onMouseOut





###### 列表

- 为网页进行合理布局，有序列表和无序列表组合嵌套使用，使页面层次分明

  |   Type   |             Key             |
  | :------: | :-------------------------: |
  | 无序列表 | `<ul> unordered list </ul>` |
  | 有序列表 |  `<ol> ordered list </ol>`  |
  | 定义列表 |  `<dl> defined list </dl>`  |
  | 菜单列表 |    `<menu> menu </menu>`    |
  | 目录列表 |  `<dir> directory </dir>`   |
  
  - 无序列表
  
    ```html
    <ul type="">
      <li type=""> name </li>
      <li type=""> name </li>
      ...
    </ul>
    ```
  
    
  
    |  key   | Explaination |
    | :----: | :----------: |
    |  disc  |   实心圆圈   |
    | circle |   空心圆圈   |
    | square |  实心正方形  |
  
  - 有序列表
  
    ```html
    <ol type="" start="" >
      <li type=""> name1 </li>
      <li type=""> name2 </li>
      ...
    </ol>
    ```
  
    - `start` ：数值，有序列表中的起始数值
    - `typr` ：可以是 数字、大小写的字母、大小写的罗马字母
  
  - 定义列表
  
    ```html
    <dl>
      <dt>product1</dt>
      	<dd>describ1</dd>
    	  <dd>describ2</dd>
      <dt>product2</dt>
      	<dd>describ1</dd>
    	  <dd>describ2</dd>
    </dl>
    ```
  

###### 表格

- 表：`<table> </table>`
- 表题：`<caption> name </caption>`
- 表头：`<th></th>` or `<thead></thead>`
- 行：`<tr></tr>`
- 格：`<td></td>` 
- 底：`<tfoot></tfoot>`
```html
<table border="100" width="600" height="200">
  <caption>表题</caption>
  <tr>
  	<th> 表头c1 </th> <th> 表头c2 </th> <th> 表头c3 </th>
  </tr>
  <tr>
  	<td> 单元格1-1 </td> <td> 单元格1-2 </td> <td> 单元格1-3 </td>
  </tr>
  <tr>
  	<td> 单元格2-1 </td> <td> 单元格2-2 </td> <td> 单元格2-3 </td>
  </tr>
  <tr>
  	<td> 单元格3-1 </td> <td> 单元格3-2 </td> <td> 单元格3-3 </td>
  </tr>
  <tfoot>
		<td> 总结： </td> <td> 总结1 </td> <td> 总结2 </td>
  </tfoot>
    <!--<caption>当然写在这也是可以的</caption>-->
</table>
```
- 合并单元格

  - 行合并：删掉其中一个单元格的代码，在另一个`<td></td>`中添加属性`colspan`即column span
  - 列合并：删掉其中一个单元格的代码，在另一个`<td></td>`中添加属性`rowspan`

  ```html
  <table border="200" width="1000" height="500" align="center">
    <caption>表测</caption>
    <tr>
        <th> 表头c1 </th>
        <th> 表头c2 </th>
        <th> 表头c3 </th>
    </tr>
    <tr>
        <td> 单元格1-1 </td>
        <td rowspan="2"> 单元格1-2 & 2-2 </td>
        <td> 单元格1-3 </td>
    </tr>
    <tr>
        <td> 单元格2-1 </td>
        <!-- <td> 单元格2-2 </td> -->
        <td> 单元格2-3 </td>
    </tr>
    <tr>
        <td> 单元格3-1 </td>
        <td colspan="3"> 单元格3-2 & 3-3</td>
        <!-- <td> 单元格3-3 </td> -->
    </tr>
    <tfoot>
        <td>总结：</td>
        <td>总结1</td>
        <td>总结2</td>
    </tfoot>
  ```


###### 浮动框架

- 内嵌框架可以在网页中直接插入其他网页或内容
  ```html
  <body>
    <iframe src="../pics/1.jpeg" name="test" width="1400" height="1100" frameborder="1" marginwidth="300"
          marginheight="100" scolling="yes">
      
    </iframe>
  </body>
  ```

- 属性：

  - 来源：src
  - 命名：name
  - 宽度：width
  - 高度：height
  - 边框：frameborder
  - 边距：marginwidth,marginheight



###### 图片

- 单标记

- `<img src="" alt="" >`

  | Attribute |                    Value                     |        Explaination        |
  | :-------: | :------------------------------------------: | :------------------------: |
  |    alt    |                     text                     |   图像显示错误的替代文本   |
  |    src    |                   URL/PATH                   |          显示的源          |
  |   name    |                     text                     |          图像名称          |
  |  height   |                   pixels/%                   |            图高            |
  |   width   |                   pixels/%                   |            图宽            |
  |   align   | top\|middle\|bottom<br />left\|center\|right |      如何在文本中排布      |
  |  border   |                    pixels                    |          周围边框          |
  |  hspace   |                    pexels                    |         左右侧空白         |
  |  vspace   |                    pixels                    |       顶部和底部空白       |
  |  usemap   |                     URL                      | 将图像定义为客户端图像映射 |

  - usemap 可以映像跳转到其他，如下
    ```html
    <img src="../pics/1.jpeg" usemap="#example">
    <map name="example">
    	<area shape="circle" croods="0,0,100" href="http://example.com" alt="example">
    </map>
    ```

    | shap Value | Explaination | coords Value                          | Explaination           |
    | ---------- | ------------ | ------------------------------------- | ---------------------- |
    | rect       | 矩形         | $x_1,y_1,x_2,y_2$                     | 矩形的两个顶点坐标     |
    | circle     | 圆形         | $x_o,y_o,radius$                      | 圆心坐标和半径         |
    | poly       | 多边形       | $x_1,y_1,x_2,y_2,...,x_n,y_n,x_1,y_1$ | 各顶点坐标（首尾相同） |


###### 音频

- `<audio src="" alt="">`
- 同img

###### 视频

- `<video src="" alt="">`
- 显示播放的控件：Control 
- 自动播放：autoplay 
- 循环播放：loop 

###### 多媒体

- 包含Midi、Mav、AIFF、SWF、AV、MP3、MOV、AVI等等
- `<embed src="" ... > </embed>`
- 自动播放：atuostart （true/false）
- 循环播放：loop（true/false）





###### 链接

- 链接的路径

  - 根路径（熟悉linux一定很清楚这个，这里的根路径一般是与网站的域名对应）
  - 绝对路径：绝对路径一般是从根目录开始
  - 相对路径：相对路径是从当前页面开始 `./` 代表当前的页面`../代表上级`

- 网址链接：
  `<a href="https://chenpeel.xyz"></a>` —— <a href="https://chenpeel.xyz">blog_github_page</a> 
  `<a href="https://zachary.world"></a>` ——<a href="https://zachary.world"> blog</a>

- 站内链接：<a href="../README.md">README</a>

- 页面书签链接：`<a href= "#name" title="" target = "_blank"> The link </a>`

  如<a href= "#key" title="跳转至Key">Key</a> 跳转到篇首Key

  |   Key   |    Explaination    |
  | :-----: | :----------------: |
  |  href   |      指向锚点      |
  | name/id |      锚点名称      |
  |  title  |   链接的提示信息   |
  | target  | 指定打开的目标窗口 |

  - target有五种值

    |   Value   |                      Explaination                      |
    | :-------: | :----------------------------------------------------: |
    |   _self   |                  在当前框架中打开链接                  |
    |  _blank   |                 在新的空白页中打开链接                 |
    |   _top    |                  在顶层框架中打开链接                  |
    |  _parent  |                   在上层框架打开链接                   |
    | framename | 在指定的框架或浮动的框架内打开链接，框架名称可以自定义 |
  
- 链接也可用于下载文件、访问FTP服务器、打开图片详情、发送电子邮件，如下
  ```html
  <a href="ftp://chenpeel.xyz"> chenpeel </a> <!-- FTP链接 仅示例 -->
  
  <a href="https://github.com/Chenpeel/Chenpeel.github.io/blob/master/imags/2.jpeg">
    <img src="https://github.com/Chenpeel/Chenpeel.github.io/blob/master/imags/2.jpeg"> 
  </a> <!-- 图片跳转 -->
  
  <a href="mailto:chenpeelalpha@gmail.com;
           ?subject=point me & ?cc=example@gmail.com & ?bcc=example@gmail.com & ?body=这周没课啦！">
    点击发送邮件
  </a>
  
  ```
  
