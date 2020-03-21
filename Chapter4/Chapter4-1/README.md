# GitBook

------

### 简介

> 自定义的博客
>
> - [GitBook 官网](https://links.jianshu.com/go?to=https%3A%2F%2Fwww.gitbook.com)
> - [GitBook 文档](https://links.jianshu.com/go?to=https%3A%2F%2Fgithub.com%2FGitbookIO%2Fgitbook)

### 准备工作

- 安装Node.js

- 安装GitBook

  ```shell
  npm install gitbook-cli -g
  ```

### 先睹为快

- 进入一个需要写博客的目录

  ```shell
  # 初始化 gitbook
  gitbook init
  ```

  将会生成:

  - `README.md`:说明文档
  - `SUMMARY.md`:book章节目录

  **注意:**每次增加目录都需要在命令行执行上述命令.

- 启动服务器,浏览器浏览

  ```shell
  gitbook serve --port 端口号
  ```

### 构建书籍

```shell
#构建书籍：默认：将生成的静态网站输出到 _book 目录
gitbook build

# 指定路径：
gitbook build [书籍路径] [输出路径]

#生成pdf格式：
gitbook pdf ./ ./mybook.pdf

#生成epub格式：
gitbook epub ./ ./mybook.epub

#生成 mobi 格式：
gitbook mobi ./ ./mybook.mobi
```



### 常用命令

```shell
    build [book] [output]       build a book
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
        --format                Format to build to (Default is website; Values are website, json, ebook)
        --[no-]timing           Print timing debug information (Default is false)

    serve [book] [output]       serve the book as a website for testing
        --port                  Port for server to listen on (Default is 4000)
        --lrport                Port for livereload server to listen on (Default is 35729)
        --[no-]watch            Enable file watcher and live reloading (Default is true)
        --[no-]live             Enable live reloading (Default is true)
        --[no-]open             Enable opening book in browser (Default is false)
        --browser               Specify browser for opening book (Default is )
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
        --format                Format to build to (Default is website; Values are website, json, ebook)

    install [book]              install all plugins dependencies
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    parse [book]                parse and print debug information about a book
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    init [book]                 setup and create files for chapters
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    pdf [book] [output]         build a book into an ebook file
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    epub [book] [output]        build a book into an ebook file
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    mobi [book] [output]        build a book into an ebook file
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
```



