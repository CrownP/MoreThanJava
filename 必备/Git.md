# 一.初始化

1. git init：初始化项目
2. git remote add origin Url ： 本地仓库关联远端
3. git push origin master : 推送到远程master分支

# 二.提交

1. git status -s ： 简单模式查看未提交文件状态
2. git add . ：提交所有变更文件到暂存区
3. git commit -m "注释" ： 提交文件到本地仓库
4. git pull --rebase ： 拉取远端，避免同时有人修改导致冲突
5. git push origin 分支名

# 三.拉取

1. git pull : 默认拉取
2. git pull origin 分支名 ： 拉取指定分支

# 四.分支

1. git branch -a ： 不带 -a 查看本地分支，加上参数查看包括远端的所有分支
2. git branch --remote ： 查看远端分支
3. git checkout 分支名 ： 切换分支
4. git checkout -b 分支名 ： 以当前分支为基础，创建并切换分支
5. git branch 分支名 -d ： 删除本地分支
6. git push origin 分支名 -d ： 删除远端分支

# 五.分支合并

1. git checkout master ： 切换分支
2. git merge --no-ff 分支名 ： 使合并分支。 --no-ff 禁止快进式合并

# 六.撤销回退

1. git add . 回退 ： git reset HEAD

# 七.认证出错

1. fatal: Authentication failed for  
   通过 git config --system --unset credential.helper 进行远端gitlab账号密码的重置
   通过 git config --global credential.helper store 进行长期保存密码