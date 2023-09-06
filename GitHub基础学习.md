

[TOC]

# 一、摘要

&emsp;&emsp;学习了Git基础命令和GitHub仓库管理，能在远程仓库里用`git clone`来下载源码到本地进行修改，通过`add`、`commit`、`push`命令逐步把本地文件上传到远程仓库，也可以用`pull`从仓库同步文件到本地。

&emsp;&emsp;建立了自己的第一个项目仓库，往后的学习心得都会放在这个仓库。

&emsp;&emsp;学会了vscode来管理本地仓库

# 二、内容

## 1）Git核心原理和工作流

### 1.1）Git核心原理

&emsp;&emsp;Git的核心原理是通过代码将远程仓库的源码下载到本地仓库，在本地仓库的操作并不会影响到远程仓库内容，如果有仓库使用权，那么可以将本地工作区的内容逐步上传到远程仓库。

**具体操作代码如下：**

远程仓库 --> 工作区（Untracked / Unstage）

- 代码：`git clone`

---

工作区 --> 暂存区（stage）

- 代码：`git add`

- **注**：可以选择需要上传的文件（比如有四个文件只想上传两个）

---

暂存区 --> 本地仓库

- 代码：`git commit`

---

本地仓库 --> 远程仓库

- 代码：`git push`

---

远程仓库 --> 本地仓库

- 代码：`git fetch`

---

本地仓库 --> 工作区

- 代码：`git diff`



### 1.2）Git工作流

1. 新建文件夹或从远程仓库克隆项目
2. 用 `git config` 命令设置作者和邮箱
   1. `git config --global user.name "Author"`
   2. `git config --global user.email xxx`
3. `git init` 初始化文件夹
4. `git status` 查看当前状态
5. `git add` 从工作区上传到暂存区
6. `git commit` 提交到本地仓库
   1. 不加 `-m` ：会打开文档编辑，编辑之后保存退出上传到本地仓库
   2. 加 `-m xxx` ：不会打开文档，直接添加提交信息后上传到本地仓库
7. `git log`：查看提交版本
8. 用 `touch .gitignore` 创建忽略文件夹，在里面写上要忽略的文件，这样就不会把该文件上传到远程仓库了
9. `git branch xxx` 创建新分支
   1. **注**：该指令并不会直接跳转到该分支，要使用 `git checkout xxx` 来进行跳转
   2. 或使用 `git checkout -b xxx` 直接新建并跳转到该分支
10. `git branch` 查看项目全部分支
11. `git commit -am “xxx”` 直接从工作区跳转到本地仓库，跳过暂存区
12. `git branch -D xxx` 删除分支
13. `git merge xxx` 合并分支
    1. **注**：该命令是将别处的分支合并到当前分支上，从其他地方合并过来





## 2）GitHub基础操作

`New repositoty`：新建仓库

如果不加生成README.md文件，那么点击 `creating a new file` 生成新文件

如果要下载源码到本地，点击右上角绿色的 `Code` 按钮

- Download ZIP 只会下载当前文件，不会下载版本历史和记录，压缩文件里没有.git文件夹
- 复制网址，使用 `git clone 网址` 下载

`git remove -v`：查看当前项目的远程仓库，push的时候能用origin代替URL

## 3）VS Code里使用Git

用vscode打开本地仓库，就可以同git一样操作本地仓库了

![image-20230906104848714](GitHub基础学习.assets/image-20230906104848714.png)

# 三、参考视频
[Git工作流和核心原理 | GitHub基本操作 | VS Code里使用Git和关联GitHub](https://www.bilibili.com/video/BV1r3411F7kn/?spm_id_from=333.337.search-card.all.click&vd_source=4aa44bc3637d6eebb58bf20e86211d23)