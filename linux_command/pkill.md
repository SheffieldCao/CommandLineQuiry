### 2.6 进程管理` pkill [options] <PATTERN> `
- ` pkill [SIGNAL] [OPTIONS] <PATTERN> ` **直接删除包含只读的文件的文件夹**
    - -9 Kill a process.
    - -1 Reload a process.
    - 15 Gracefully terminate a process.

- ` pkill '^<NAME>$' ` **严格限定名称为` NAME `**

- ` pkill -9 <NAME> ` **Kill本用户包含` NAME `的全部进程**

- ` pkill -9 -f <NAME> ` **扩展` PATTERN `搜索范围到整个进程列表**

- ` pkill -9 -u [USER1],[USER2]... <NAME> ` **Kill`USERx`的包含 NAME 的全部进程**

- ` pkill -9 -n/-o <NAME> ` **Kill最新创建的/最老创建的NAME进程**