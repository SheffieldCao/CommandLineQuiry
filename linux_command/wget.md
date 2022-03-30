### 2.4 Wget 下载文件

- ` wget -O [NAME] [URL] ` **下载到指定名称**

- ` wget –c [URL] ` **继续未完成的下载**

- ` wget –b [URL] ` **后台进程下载**

- ` wget –I URL.txt ` **下载指定文件中的URL全部文件**
    ```shell
    vi url.txt
    wget -I url.txt
    ```

- ` wget - - tries=100 [URL] ` **下载尝试次数**

- ` wget –r –A.txt [URL] ` **只下载某一类文件**

- ` wget --reject=png [URL] ` **不下载某一类文件**

- ` wget --ftp-user=[USER] --ftp-password=[PASSWORD] [URL] ` **使用FTP登录并下载**