# [Git入门] git本地仓库
Git是开启GitHub的一把钥匙，它会为程序员解决代码版本控制的问题
### 基本操作
前提条件：git的6行配置 git config
~~~
git config --global user.name 你的英文名
git config --global user.email 你的邮箱
git config --global push.default simple
git config --global core.quotepath false
git config --global core.editor "code --wait"
git config --global core.authorcrlf input
~~~
需要注意的是，上述的英文名及邮箱可与GitHub不保持一致
git init：初始化，创建 .git目录
git add 路径：选择那些变动是需要提交的，路径可是绝对也可相对
.gitignore：把不需要提交的文件名输入该文件内容里，会使里面的文件不放进git库
git commit -m 字符串：提交并说明理由，字符串有空格需要用引号包起来
git commit -v：会帮助我们回顾修改的地方以及需要写注释，对于新手来讲很友好
git log:查看提交了多少版本
git status -sb:查看具体操作情况
git reset --hard XXXXXX：跳回某一个版本，后面跟commit号，commit号可用git log查看，但需要注意的是，跳回某一个版本后，其后面修改的版本将会用git log查看不到
git reflog：查看所有历史，包括跳回后的各种版本
删除文件的步骤：
1. rm 文件名
2. git add 文件名
3. git status（查看是否修改）
4. git commit -v
### 开创两条分支
git branch x：基于当前最新提交的版本开一条分支，所以使用该命令时需要git commit一次
git checkout x/master：切换进入x/master分支
git branch -d 分支名：删除分支
### 合并分支
1. 进入需要保留的分支，一般选master
2. git merge x 解决冲突
3. 删除无用的分支git branch -d x
4. git add 文件名
5. git commit
如果合并时出现冲突，自行修改提示的冲突部分再提交