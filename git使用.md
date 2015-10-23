#Git使用教程
##1. 安装git  
1. 网址http://git-scm.com/download/win, 选择 64-bit Git for Windows Setup.  
2. 除安装路径,其余全部默认即可  
3. 右击菜单中如果有git gui here和git bash here则安装成功


##2. 在idea中集成  
1. file--setting--version control--git,右侧选择path to git executetable.选择本地的git.exe,如G:\worksoft\Git\bin\git.exe,选择test,弹出成功即可  

##3. 使用git
1. 在任意位置新建文件夹作为git起始目录  
2. 在创建的文件夹内右击选择Git Bash here,输入git init,会在当前文件夹生成.git文件.  
3. 进入idea,选择vcs--checkout from version control--git  
4. 复制公司的项目托管地址,粘贴到git repository url,选择test,弹出成功即可  
5. parent directory选择刚刚创建的目录 directory name输入项目名称,点击clone  
6. 右上角出现maven projects need to be improted,选择import changes  

##4. push & pull  
注意:右击项目,如果没有出现git说明项目没有和git关联上,查看项目所在的目录有没有.git文件夹  
###push
1. 右击要提交的文件--git--if("第一次提交"){选择add}else{commit file},此步骤为提交到git(这个步骤还没理解,还可能为提交到本地仓库,还需要同步到github上)  
ps:一定要输入提交信息
2. 右击刚刚的文件--git--repository--push  

###pull  
1.选择要pull的文件 右击--git--repository--pull  

##5. 错误