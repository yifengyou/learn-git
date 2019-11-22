# 使用repo管理多个Git仓库

## repo简介

* Android 使用 Git 作为代码管理工具，开发了 Gerrit 进行代码审核以便更好的对代码进行集中式管理，还开发了 Repo 命令行工具，对 Git 部分命令封装，将百多个 Git 库有效的进行组织。


## 基本概念

### 清单库

* 一个清单库可以包含多个清单文件和多个分支，每个清单文件和分支都有对应的版本。清单文件以xml格式组织的。举个例子：

1. remote元素，定义了名为korg的远程版本库，其库的基址为git：//172.16.1.31/
2. default元素，设置各个项目默认远程版本库为korg，默认的的分支为gingerbread-exdroid-stable。当然各个项目(project元素)还可以定义自己的remote和revision覆盖默认的配置
3. project元素，用于定义一个项目，path属性表示在工作区克隆的位置，name属性表示该项目的远程版本库的相对路径
project元素的子元素copyfile，定义了项目克隆后的一个附件动作，从src拷贝文件到dest


## 命令格式


```
repo <COMMAND> <OPTIONS>
```











## 参考

* <https://blog.csdn.net/sunweizhong1024/article/details/8987494>
* <http://wiki.jikexueyuan.com/project/android-source/using-repo.html>
