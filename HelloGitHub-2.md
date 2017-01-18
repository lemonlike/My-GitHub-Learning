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