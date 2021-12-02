
## 断点
```

c 去下一个断点
info b 查看所有断点

```
### 在文件行号上打断点
这个比较简单，如果要在当前文件中的某一行打断点，直接b linenum即可
也可以显式指定文件，b file:linenum

gdb会对所有匹配的文件设置断点。你可以通过指定（部分）路径，来区分相同的文件名：
(gdb) b a/file.c:6

### 产看函数调用栈
```
bt

“bt full”命令显示各个函数的局部变量值
“bt full n”，意思是从内向外显示n个栈桢，及其局部变量
```

### 打印函数局部变量的值
```
(gdb) info locals
```

### 查看当前位置
```
where
```

### 打印源代码行
```
list命令可以指定行号，函数：
(gdb) l 24
(gdb) l main

还可以指定向前或向后打印：
(gdb) l -
(gdb) l +

还可以指定范围：
(gdb) l 1,10

```
### 打印变量的类型
```
(gdb) ptype var
```

### “set print pretty on”命令，这样每行只会显示结构体的一名成员，而且还会根据成员的定义层次进行缩进
```
(gdb) set print pretty on
(gdb) p st
```
