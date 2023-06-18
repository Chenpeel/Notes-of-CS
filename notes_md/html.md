## Web标准：

1. **结构** ：HTML -> 页面元素
2. **表现** ： CSS -> 页面样式
3. **行为** ： JavaScript -> 页面交互的动态效果

## HTML

###### 超文本标记语言（Hyper Text Markup Language）

- 载入内容,包括文本、音频、图片等等

#### Key

###### 标题

- `<title>显示在网址栏标题</title>`

###### 注明文件

- `<!DOCTYPE html>`
- 注明文件类型为html

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
    



###### 标签与标签之间的关系

父子关系（嵌套关系）

- eg.

	```html
  <head>
  	<title></title>
  </head>
	```

   

- 兄弟关系（并列关系）

  - eg.

    ```html
    <head></head>
    <body></body>

###### h系列

- `<h1></h1>`

- `<h2></h2>`

- `<h3></h3>`

- `<h4></h4>`

- `<h5></h5>`

- `<h6></h6>`

###### 换行&水平线

- `<br>`
- `<hr>`

###### 文本格式化

|  说明  | 标签  |    标签    |
| :----: | :---: | :--------: |
|  加粗  | `<b>` | `<strong>` |
| 下划线 | `<u>` |  `<ins>`   |
|  倾斜  | `<i>` |   `<em>`   |
| 删除线 | `<s>` |  `<del>`   |

- 简洁普适，增长强调

###### 注释

-  `<!--注释-->`
- 浏览器不会渲染

###### 图片

- `<img src="" alt="" title="" width="">`
- Src是路径，alt是报错提示...

###### 音频

- `<audio src="" alt="">`
- 同img

###### 视频

- `<video src="" alt="">`
- Control 显示播放的控件
- autoplay 自动播放
- loop 循环播放

###### 链接

- <a href="http://chenpeel.xyz">blog_github_page</a>
- <a href="http://zachary.world"> blog</a>
- `<a herf= "#" target = "_blank">new table</a>`







## CSS 
###### 级联样式表 （Cascading Style Sheet）

- 外观格式设计，解决网页内容和表现分离





## JavaScript

######  客户端脚本语言

- 核心（ECMAScript）
- 文档对象模型（Document Object Model,DOM）
- 浏览器对象模型（Brower Object Model,BOM）

