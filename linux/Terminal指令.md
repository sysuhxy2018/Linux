# Terminal指令

### mkdir path

如果是多级目录，则需要 -p ，表示递归创建目录


``` shell
xinyuan@xinyuan-VirtualBox:~/Desktop$ mkdir bleach/rukia
mkdir: cannot create directory ‘bleach/rukia’: No such file or directory
xinyuan@xinyuan-VirtualBox:~/Desktop$ mkdir -p bleach/rukia
```

### rmdir path

这个是删除目录（文件夹）的，删除文件用rm。必须确保要删除的目录为空。

就算用 -p ，那也要确保每次删除完一个目录后上级目录为空，即上级目录只有一个它子目录。

### touch file

创建新文件

### rm file

删除文件，删除目录用rmdir。

### cp source dest

复制文件或目录。有几种组合：

* 文件到文件，目标文件可以不存在。目标文件名可以不一致，但后缀名最好一致。如果不存在，就会自动创建。如果存在，就会自动覆盖。如果不想自动覆盖，可以用 -i （询问是否覆盖，回答 y/n）或 -u（如果目标文件存在，且比源文件要旧，才复制）参数。
* 文件到目录，那么只能自动创建新的同名文件。
* 目录到目录，不管源目录是否为空，必须要添加 -r 参数，表示递归复制。

``` shell
xinyuan@xinyuan-VirtualBox:~/Desktop$ cp bankai bleach/rukia
cp: -r not specified; omitting directory 'bankai'
xinyuan@xinyuan-VirtualBox:~/Desktop$ cp -r bankai bleach/rukia
xinyuan@xinyuan-VirtualBox:~/Desktop$ cp dream.txt bleach/rukia/dream.txt
xinyuan@xinyuan-VirtualBox:~/Desktop$ cp -i dream.txt bleach/rukia/dream.txt
cp: overwrite 'bleach/rukia/dream.txt'? n
xinyuan@xinyuan-VirtualBox:~/Desktop$ cp -u dream.txt bleach/rukia/dream.txt
xinyuan@xinyuan-VirtualBox:~/Desktop$ cp dream.txt bankai/btw.dat
```

### mv source dest

移动文件或目录，如果目标文件存在，则自动覆盖。类似于cp，可以理解为是“剪切”，即如果复制成功，源文件/目录会删除。

### chmod xyz path/file

修改目录或文件的权限，常见的权限码有666，777（最高）等。

<hr>

### 关机

* shutdown
* who，查看在线用户

### 文件和目录

* 文件：touch/rm	
* 目录：mkdir/rmdir/cd
* 公共：ls/cp/mv
* 权限：chmod，文件默认为666，目录为777（最大）。

### 文件

* cat/tac
* more/less，分页
* head/tail，查看前几行/最后几行。
* whereis/locate/find，文件迅速查找
* gzip/tar，tar支持多文件打包再压缩

### 正则

* grep，文件内容正则匹配
* printf，格式化输出
* awk，以行为单位进行正则匹配

### 进程

* ps，查看进程
* pstree，查看进程树
* top，实时显示进程消息。
* netstat，查看占用端口的进程。






