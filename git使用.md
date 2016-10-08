#Git使用教程
##1. 安装git  
1. 网址http://git-scm.com/download/win, 选择 64-bit Git for Windows Setup.  
2. 除安装路径,其余全部默认即可  
3. 右击菜单中如果有git gui here和git bash here则安装成功


##2. 在idea中集成  
1. file--setting--version control--git,右侧选择path to git executetable.选择本地的git.exe,如G:\worksoft\Git\bin\git.exe,选择test,弹出成功即可  

##3. git的使用之前的说明(理念,必读)  
git和svn不同,git需要每个人都有一个单独的分支,每次提交到自己的分支上,如果B需要你的代码,则首先将你的代码merge(合并)到一个类似测试版本上(测试版就是一个分支而已)接着B将他的分支切换到测试版本,然后拉代码.当需要发布正式版的时候再将测试版的代码合并到master上.
##4. 使用git
1. 在任意位置新建文件夹作为git起始目录  
2. 在创建的文件夹内右击选择Git Bash here,输入git init,会在当前文件夹生成.git文件.  
3. git remote add origin "远程的地址" (这步是添加一个远程仓库的地址)  
4. git fetch origin (这步是同步远程仓库的信息)  
5. git checkout nmw_zn (nmw_zn是分支名,根据自己的分支改动)  
 

下面的4步放弃,最好用命令行操作git  
==
3. 进入idea,选择vcs--checkout from version control--git  
4. 复制公司的项目托管地址,粘贴到git repository url,选择test,弹出成功即可  
5. parent directory选择刚刚创建的目录 directory name输入项目名称,点击clone  
6. 右上角出现maven projects need to be improted,选择import changes 


##5. push & pull  
注意:右击项目,如果没有出现git说明项目没有和git关联上,查看项目所在的目录有没有.git文件夹  
###push
1. 右击要提交的文件--git--if("第一次提交"){选择add}else{commit file},此步骤为提交到git(这个步骤还没理解,还可能为提交到本地仓库,还需要同步到github上)  
ps:一定要输入提交信息
2. 右击刚刚的文件--git--repository--push  
 
###命令行操作方式如下  
####提交所有的改动  
1. git add . (这步我也不清楚,先用)  
2. git commit -m"test"(-m的意思是可以不写提交信息,""里的内容为提交信息)  
3. git push(提交到远程仓库)  
 
####提交指定的文件  
1. git commit -a(提交到git,会打开vi编辑器,先按i键进入编辑模式,查看哪个需要提交的,将前面的#去掉),好了之后按ESC,:wq保存退出,放弃是Esc,:q退出  
2. git push


###pull  
1.选择要pull的文件 右击--git--repository--pull  

##7. 拉meger的代码  
1. 合并meger和自己代码,源代码meger,目标自己的分支  
2. pull  
3. 如果自己有代码没提交的,在合并之前之后操作都可以,一般不会被冲掉.


##8. .gitignore文件  
1. 必须使用命令行操作,在项目根路径右击 git bash here,输入touch .gitignore  
2. 可以vim编辑,也可以在idea里操作  
/.idea/(忽略.idea文件夹下的所有文件)  
*.iml(忽略所有.iml结尾的文件)  


注:如果之前已经push过,.gitignore是没有用的,需要清除关联的缓存  
步骤:  
    1. git rm --cached .idea/(清除.idea下所有的缓存,递归的话需要-rf)  
    2. 输入git commit -a 将相应的#号去掉  
    3. 别忘了写.gitignore文件  
    
##9.更换远程仓库  
---------------------------------------------------------  
1. 删除之前的.git文件  
2. git init  
3. git remote add origin 仓库地址  
4. git fetch origin 
5. git checkout master
6. git add .  
7. git commit -m "project init"(-m可以不写,""里为提交信息)  
8. git push master  
解释:第四部是将远程仓库拉倒本地仓库,需要第5部将代码从本地仓库拉出来
---------------------------------------------------------  
上面的删除,使用下面的命令即可
git remote set-url origin 仓库地址

##10. 更换分支  
1. 创建分支:直接在网站上创建新的分支  
2. git fetch origin(同步远程仓库的分支)  
3. git pull(再拉一次项目,保证正确)  
4. git checkout "分支名"  

##11. 错误
1.在本地仓库中,但是没有提交到远程仓库,需要删除那个文件,再pull


##12. 解决冲突
1. git checkout merge(冲突的分支名)(作用:切换到merge分支)
2. git pull(将分支的代码拉取到本地)
3. git checkout nmw_zn(切换回分支)
4. git merge merge(merge合并到nmw_zn上,要在nmw_zn上执行操作)
5. git commit -a -m "fix commit"(提交到本地)
6. git push(提交到远程仓库)


##13. 删除已经在线上的文件或文件夹
git rm -r --cached 
git add .
git commit -m 'update .gitignore'

-r 递归, --cached后面跟文件或文件夹,需要相对.gitignore路径
