# Git使用指南
**Git本地环境配置**  
1、可以在命令行里输入以下命令确认安装情况：  
>git --version  
2、启动 Git，在命令行终端输入：
>git help  
3、设置Git  
1) 用户名和 email（必须设置）  
>git config --global user.name "雨知" # 请换成你自己的名字  
>git config --global user.email "sushi.li@alipay.com" # 请换成你自己的邮箱  
2) 其他设置  
不论 Windows 还是 Linux 还是Mac，建议至少config下述内容：  
>git config --global push.default simple # 我们要求 Git 版本 1.9.5 以上  
若是 Linux 还是Mac，建议至少config下述内容：  
>git config --global core.autocrlf false # 让Git不要管Windows/Unix换行符转换的事。  
Windows上还需要配置：  
>git config --global core.ignorecase false # 设置大小写敏感  
**查看设置**  
>git config --global --list  
4、创建SSH Keys  
1) 登录 GitLab ，在左边的菜单点击“profile settings”，继续点击“SSH Keys”  
2) 然后点击绿色按钮 “+ Add SSH Key”  
3) 请按网页上the SSH help page这个链接（见截图）指向的文档中的说明，在本地命令行里生成SSH Key。然后把它复制到上述网页。然后提交表单即可  
**检查key是否配置准确**
>ssh git@..........  
如果返回用户的用户名，则表示配置正确。如果返回Permission denied (publickey),那么请在本机补充运行  
>ssh-add
  
**推荐使用Wins10的Linux子系统（Ubuntu xxx LTS），Wins10自带powershell也可用**  
使用子系统注意事项：不要使用windows的文件浏览器进行文件的新建、删除、复制、剪切、重命名等操作。涉及到文件的操作都需要在子系统内进行。 即文件管理层面的操作，需要在子系统内进行。但是文件的编辑，可以在windows层面进行。因为子系统的文件系统和windows的文件系统是单向同步的，即子系统文件系统->同步至windows文件系统。反过来不行。）

**主要使用命令行：**  
1、git clone git@gitlab.alibaba-inc.com:energy_MPCO/engine_ctrl_pidTuneOnline.git ##把远端代码库下载到本地  
2、git checkout linyun ##进入自己的开发分支（需cd到clone的repository下；克隆的库默认放在subsystem的路径，如：C:\Users\Jamie\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu18.04onWindows_79rhkp1fndgsc\LocalState\rootfs\home\jamie\engine_ctrl_pidTuneOnline）  
3、git add -A   ##开发完成后，添加所有更改过的文件  
4、git commit -m "一段描述，描述做的修改"   ##提交修改备注  
5、git push   ##将修改上传至远端代码库  
6、git branch   ##查询目前位于哪个branch

**提交相关：**  
git add a.vm //添加某个文件到本地暂存区   
git add . //添加所有目录下修改过的文件   
git rm a.vm //移除某个文件，和git add 相反   
git status //用来查看当前工作区的状态   
git commit -m "feat：增加构建文件类型说明" //提交并增加提交注释，非常重要且常用的命令。用于将所有通过 `git add`暂存的文件，提交到本地库。

**本地和服务器仓库交互：**  
git fetch //获取远程仓库的代码   
git pull //相当于git fetch + git merge   
git push //常会用到的命令，用于将本地的文件推送到服务器上  

**分支相关：**  
git branch //查看分支状况   
git branch -h //查看其他的命令   
git checkout develop-branch //用来切换分支   
git log //查看历史   
git stash //用来临时存放暂不打算提交的文件   
git tag //为代码的历史记录某个点打个标签，一般用来标记发布的版本   
git cherry-pick //用于将另一个分支的某次提交代码，合并到当前分支   
git rebase //用于将另一个分支的最新代码，全量合并到当前分支  
