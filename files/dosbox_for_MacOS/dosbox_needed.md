# DosBox Needed tools

#### Introduction 

1. 首先需要的就是Dosbox这个工具，可以使用terminal的homebrew包管理工具下载`brew install dosbox`
2. 通过homebrew下载的dosbox是没有编译和链接程序的，需要额外的[下载](./)，三个文件任选其一下载解压即可，[默认下载](./dosbox_needed.zip)的是`.zip`
3. 下载完成后将其放在一个文件夹，并移动到方便操作的地方，为了便于启动dosbox后进行mount挂载操作
4. 挂载：
   - 在dosbox中输入挂载指令`mount  C /Users/your_user_name/xxx` 将虚拟的C盘挂载到你的 `/用户/此用户/存放上述下载的文件夹`，
   - 再输入`cd  C: ` 切换到挂载目录
5. 编写程序、编译、链接、运行：
   - 编写程序可以在VSCode / Vim中进行，我是在我的挂载目录中创建文件夹`code`把所有源程序文件放入其中，编写好再进行挂载
     - 也可以在dosbox挂载目录中输入`edit`（必须是在含有edit.com的目录下才可以进入编辑器）,然后打开或创建文件，编辑
   - 编译：在含masm.exe目录下
     - 输入`masm  code\file.asm   \target_directory\file.obj`
       - 注意：Linux/Unix 和Windows的目录层级 ,Linux/Unix是使用`/` 而Windows是使用`\` 
       - 后面`\target_directory\file.obj`含义是：编译后的obj文件存储到目标目录，可以省略，就是保存到`masm.exe`的同级目录
   - 链接：在含有link.exe目录下
     - 输入`link \target_directory\file.obj  \target_directory\file.exe`,将obj链接成可执行程序
   - 执行：在保存`file.exe`的目录下
     - 输入`file`或者`file.exe`
     - 亦或在debug.exe文件层级输入`debug  target_directory\file.exe`进行debug的单步运行
6. 解释：下载的压缩包中的一些如lib 的文件，在编译和链接时是可能用到的库或是其他可能用到的文件
   慎重，注意不要在懒得敲 你的`target_directory\file.asm`之后删除的时候 误删了

