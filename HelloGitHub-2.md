# 其他一些Git中经常使用的指令

标签： GitHub

---

- `git pull origin master` 从远程库获得更新
- `git log --graph` 以图表形式查看分支
- `git reset --hard` 只要提供目标时间点的哈希值，就可以回溯到该时间点的状态
- `git reflog` 查看当前仓库的操作日志
- `git commit --amend` 修改提交信息
- 如果没有新的文件被添加，只是修改了文件，则在提交时候可以直接使用 `git commit -am "some changes"` 等同于 
> `git add`  
> `git commit -m "some changes"`

- `git rebase -i` 压缩历史 *（这个以后再看）*

## 详解push —— 推送至远程仓库
- 推送至master分支
使用指令`git push -u origin master`
-u参数可以在推送的同时，将origin仓库的master分支设置为本地仓库当前分支的**upstream（上游）**。添加这个参数，将来`git pull` 时，就可以直接从origin的master分支获取内容，省去了另外添加参数的麻烦。

- 推送至master以外的分支
在本地创建develop `git checkout -b develop` 将它push给远程仓库并保持分支名不变 `git push -u origin develop`
现在，在远程仓库的GitHub页面就可以查看到develop分支了

## 详解pull —— 从远程仓库获取
**前提：我们把远程仓库clone到本地，远程仓库包括master和develop两个分支，clone到本地后实际本地的只是一个master分支**  

- 获取远程的develop分支  
`git checkout -b develop origin/develop` -b 后面的develop是新建的本地分支名称 origin/develop 是新建本地分支来源的分支名称
接下来就可以在本地的develop下进行开发，然后`git commit -am "Add develop"` 最后 `git push`
通过以上操作就可以和其他开发者互相合作，共同培育develop分支了。

**如果远程仓库的develop分支被他人修改了，则需要pull最新的develop分支到本地，使用命令 `git pull origin develop`**


**更多关于push pull的相关内容 请参考[Git push与pull的默认行为](https://segmentfault.com/a/1190000002783245)**

## 设置SSH Key
*SSH应该在最开始使用github时进行设置*  
`ssh-keygen -t rsa -C "your_eamil@exmaple,com"` 邮箱为你创建github账户所用的邮箱。  
`ssh -T git@github.com` 用目前的私有密钥与github进行认证和通信。

## 怎么在pycharm中使用git和github
嗯 这个很简单，只需要在settings中填一下Git和GitHub相关配置即可。不过对仓库的操作最好还是使用Git Bash的命令行，这样对整个流程会有更深刻的认识。