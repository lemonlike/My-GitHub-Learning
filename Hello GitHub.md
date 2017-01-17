# Hello GitHub

标签（空格分隔）： GitHub

---

最近刚开始看GitHub的相关内容，毕竟GitHub可以说是全球最大的开源社区了，作为一名计算机专业的学生，怎么能不了解它呢？
接下来我就开始记录一下目前已经了解到的关于GitHub方面的知识。
## 先从Git入手
目前我应该对GitHub了解还是很“肤浅”的，我现在所理解的GitHub如下：
GitHub是基于Git的，Git面向本地，它是针对本地开发项目的一个种版本控制系统，一个项目对应一个仓库repository。而GitHub为Git增添了社交功能，你可以把你的仓库push到网上，全世界的程序员都可以看到你的项目，并且可以对你的项目提出问题、复制、申请修改等，可以说是真正意义上实现了项目开源。
貌似废话说的有点多了，我写的不是“教程”，而是一些零碎的笔记。。

### 在本地创建一个仓库的完整流程
新建一个文件夹，例如名字叫 `test`，cd 到 `test` 目录下 新建一个文件a.md 

- `git init`命令 将test文件夹初始化为一个仓库
- `git status`命令 查看当前git仓库的状态
- `git add` 如果对a.md文件做了修改，则使用此指令将文件提交到缓冲区
- `git commit` 使用此指令将缓冲区的文件提交到仓库；一般情况下使用格式为 `git commit -m 'first commit'` 其中-m 表示提交的信息，引号为信息内容。
- `git log` 查看提交日志
- `git diff` 查看工作树（最新的代码）与暂存区的差别 （在git add 之前），如果已经git add了，则使用`git diff HEAD` 查看工作树和最新提交的差别（在git commit之前）。
- **分支branch**
 - 创建一个分支aa并切换到aa： `git checkout -b aa` 也可以使用两步完成 `git branch aa` `git checkout aa`
 - 分支间的切换：`git checkout -` 切换到上一分支。
- **合并分支merge** 
 - 必须先切回到master分支上，然后`git merge aa` 看书上说最好使用`git merge --no-ff aa` 加上--no-ff 参数是为了在历史记录中明确记录下本次分支合并，我们需要创建合并提交。*（但是我并没有搞明白在编辑提交界面如何退出。。）*
这就是在本地使用git创建一个仓库和提交的流程。