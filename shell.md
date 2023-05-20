# Shell

## 从第一行开始

- 此行称为[shebang](https://en.wikipedia.org/wiki/Shebang) （sharp(#) + bang(!)的意思），指引操作系统运行文件
- `#!/bin/bash`或`#!/bin/zsh` 是指定特定的程序来执行

```shell
#!/bin/bash
#!/bin/zsh
```

## 变量

- shell默认变量全都是字符串

### 变量赋值及引用

- 使用变量无需事先声明
- 命名遵循`<tt>[a-zA-Z_][a-zA-Z0-9_]+`，即大小写字母数字和下划线组成（不能以数字开头）
- 等号的左右都不能有空格
- 引用时须变量前加`$`
- 引用时变量可能会与其他文字混淆

```shell
varname="val1"

num=2
echo "This is the $numnd" #由于可能引起歧义,使用符号{}来区分
echo "This is the {$num}nd" #放歪了 ，勿手残
echo "This is the ${num}nd" #加在$所引用的变量前
```



### 变量算术

- 由于变量都是字符串，那么直接尝试加肯定不会如意

  ```shell
  var=1
  var=$var+1
  echo ${var}  # 这里的输出是"1+1"
  ```

- “好孩子写法”----C语言风格

  ```shell
  var=0
  ((var += 1))
  ((var++))
  echo ${var}  # 2
  ((var = var * var))
  echo ${var}  # 4
  let  'var=var/3'  #整数除法，向0舍入，1
  echo ${var}  # 1
  echo $((var+=2)) # 3
  var=$((var-1))
  echo $var    # 2
  ```

- 甚至有人用expr之类的外部程序，杀鸡焉用牛刀。。

  ```shell
  var=1
  var=$(expr "$var"+1)
  echo $var #然而输出是"1+1"
  echo var=`expr "$var"+1`
  echo $var #然而是"1+1+1"
  ```

## 流程控制

### if语句

- `[-f "./test.sh"]` 判读是否是一个文件
- `[-x "/bin/ls"]` 判断是否存在并有可执行权限

```shell
if [ -f "./ins.sh" ]; then
    echo "yes"
elif [ -f "./test.sh" ]; then
    echo "no"
else
    echo "other"
fi
```

### `&&`和`||`



### case语句

### select循环语句

### while/for循环



