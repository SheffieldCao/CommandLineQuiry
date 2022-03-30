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