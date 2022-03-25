# CommandLineQuiry

## 1 Miniconda

### conda环境操作
- ` conda create -n NAME python==2.8.5 ` 创建环境(使用 python 版本3.8.5)
- ` conda remove -n NAME --all ` 移除环境

### pip安装

- ` pip install NAME==[Version] -f [URL] `

## 2 Linux 命令

### 2.1 软连接 ` ln [options] src dst `
- -v 显示详细的处理过程
- 创建软链接
  - ` ln -s [src] [dst] `
    ` ln –s /var/www/test test `

- 删除软链接删除都是使用rm来进行操作
  - ` rm –rf NAME `（请注意不要在后面加` / `，` rm –rf ` 后面加不加` / `的区别，可自行去百度下啊）
  ` rm –rf test `

- 修改软链接
  - ` ln –snf [src] [dst] `
  创建一个软链接
  ` ln –s /var/www/test /var/test `
  修改指向的新路径
  ` ln –snf /var/www/test1 /var/test `

### 2.2 文件复制 ` cp [options] source dest `
- ` cp -r ./data /mnt/sdf/usr/datasets ` **复制文件**
  - r：若给出的源文件是一个目录文件，此时将复制该目录下所有的子目录和文件。
  - a：此选项通常在复制目录时使用，它保留链接、文件属性，并复制目录下的所有内容。其作用等于dpR参数组合。
  - p：除复制文件的内容外，还把修改时间和访问权限也复制到新文件中。
- ` cp -l source dest ` **只生成链接**
  - l：不复制文件，只是生成链接文件。**等价于软链接生成**
- ` cp -f source dest ` **是否覆盖**
  - f：覆盖已经存在的目标文件而不给出提示。
  - i：与 -f 选项相反，在覆盖目标文件之前给出提示，要求用户确认是否覆盖，回答 y 时目标文件将被覆盖。

### 2.2 文件压缩与解压缩

#### zip ` zip [options][-b <工作目录>][-ll][-n <字尾字符串>][-t <日期时间>][-<压缩效率>][压缩文件][文件...][-i <范本样式>][-x <范本样式>]`
- ` zip -r dest.zip src ` **压缩` src `下的全部文件到` dest.zip `**
- ` zip -dv cp.zip a.c ` **将 ` cp.zip `中的` a.c `文件删除**
- ` zip -sf test.zip ` **查看压缩文件夹结构**
- options
  - A 调整可执行的自动解压缩文件。
  - b<工作目录> 指定暂时存放文件的目录。
  - c 替每个被压缩的文件加上注释。
  - d 从压缩文件内删除指定的文件。
  - f 更新现有的文件。
  - F 尝试修复已损坏的压缩文件。
  - g 将文件压缩后附加在既有的压缩文件之后，而非另行建立新的压缩文件。
  - i<范本样式> 只压缩符合条件的文件。
  - J 删除压缩文件前面不必要的数据。
  - L 显示版权信息。
  - m 将文件压缩并加入压缩文件后，删除原始文件，即把文件移到压缩文件中。
  - n<字尾字符串> 不压缩具有特定字尾字符串的文件。
  - r 递归处理，将指定目录下的所有文件和子目录一并处理。
  - S 包含系统和隐藏文件。
  - t<日期时间> 把压缩文件的日期设成指定的日期。
  - T 检查备份文件内的每个文件是否正确无误。
  - u 与 -f 参数类似，但是除了更新现有的文件外，也会将压缩文件中的其他文件解压缩到目录中。
  - v 显示指令执行过程或显示版本信息。
  - x<范本样式> 压缩时排除符合条件的文件。
  - y 直接保存符号连接，而非该连接所指向的文件，本参数仅在UNIX之类的系统下有效。
  - z 替压缩文件加上注释。

#### tar ` tar [options] dest.tar.gz src `
- ` tar -czvf test.tar.gz a.c ` 压缩文件
  - c 创建新的备份文件
  - v或--verbose 显示指令执行过程
  - z或--gzip或--ungzip 通过gzip指令处理备份文件

- ` tar -tzvf test.tar.gz ` 显示压缩文件内容
  - -t或--list 列出备份文件的内容。

- ` tar -xzvf test.tar.gz ` 解压缩
  - -x或--extract或--get 从备份文件中还原文件。

### 2.3 Wget 下载文件

- ` wget -O [NAME] [URL] ` **下载到指定名称**

- ` wget –c [URL] ` **继续未完成的下载**

- ` wget –b [URL] ` **后台进程下载**

- ` wget –I URL.txt ` **下载指定文件中的URL全部文件**
    ```shell
    vi url.txt
    wget -I url.txt
    ```