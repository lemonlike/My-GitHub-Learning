# Hello GitHub

标签：GitHub

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
- `git diff` 查看工作树（最新的代码）与暂存区的差别 （在`git add` 之前），如果已经`git add`了，则使用`git diff HEAD` 查看工作树和最新提交的差别（在`git commit`之前）。
- **分支branch**
 - 创建一个分支aa并切换到aa： `git checkout -b aa` 也可以使用两步完成 `git branch aa` `git checkout aa`
 - 分支间的切换：`git checkout -` 切换到上一分支。
- **合并分支merge** 
 - 必须先切回到master分支上，然后`git merge aa` 看书上说最好使用`git merge --no-ff aa` 加上--no-ff 参数是为了在历史记录中明确记录下本次分支合并，我们需要创建合并提交。*（但是我并没有搞明白在编辑提交界面如何退出。。）*
这就是在本地使用git创建一个仓库和提交的流程。

## 怎么向GitHub提交代码
### 情景一：我在GitHub上已经建好了仓库甚至已经写了一些代码了，我想clone到本地，再开发。
首先进入我们本地的一个文件夹里，然后使用命令`git clone git@github.com:lemonlike/test.git` 这条命令将本地与GitHub上的仓库关联，并且将GitHub上test仓库clone到本地了。接下来你可以随意在test目录中修改增添删除文件，然后进行commit，之后就可以使用命令`git push origin master` 进行代码提交。
### 情景二：我想把本地的仓库提交到GitHub上
首先在自己的GitHub上新建一个test仓库，然后在本地的test仓库目录下 使用命令 `git remote add origin git@github.com:lemonlike/test.git` 这条命令的意思就是给本地test仓库指定一个远程仓库， 这个远程仓库的地址就是 git@github.com:lemonlike/test.git
接下来 用命令`git push origin master` 就可以向GitHub提交代码了。

查看当前项目有哪些远程仓库可以使用命令：`git remote -v`
提交代码前应设置自己的用户名和邮箱，这些信息会显示在所有的commit记录里，执行下面的命令就可以了（以我自己的为例）：
`git config --global user.name "lemon"`
`git config --global user.email "xxxx@qq.com"` *（他们说用QQ邮箱很low，为什么？ 我并没觉的。）*
## 怎么向别人的仓库贡献代码(pull Requests)

第一步：登录自己的github账号，找到一个自己感兴趣的项目，点击项目右上角的Fork，然后项目就出现在自己的Repository里。
第二步：将项目clone到本地，增添自己想修改的东西，commit后再push到自己的github上。
第三步：点开自己github中Fork过来的项目，再点击pull Requests，在这个界面可以看到该项目与原有项目的不同之处，同样写好标题和描述后点击确定就完成了我们对该项目的一个PR。

