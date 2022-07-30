### git和本地建立ssh免密
- ssh-keygen -t rsa -C "errorl@126.com" //本地文件夹建立.ssh文件夹
- clip < ~/.ssh/id_rsa.pub //直接赋值粘贴 .ssh的文件会破坏格式，在文件夹下打开git bash，复制id_rsa.pub下内容
- 进入github，点击头像，选择settings-》ssh keys 》 add new, 在key下粘贴上述内容 》add ssh key
在gitbat 验证是否能成功登陆 
- ssh -T git@github.com 登录
     
### Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.
idea 使用个人token登录 而不再是用户名密码了
refer：https://blog.csdn.net/yjw123456/article/details/119696726

**生成令牌**
- setting >> Developer settings >>点击Personal access tokens(个人访问令牌) >> Generate new token >>点击Generate token生成令牌 >>copy token
- git remote set-url origin https://xxx@github.com/xiaoyuJane/leetcode.git //将token放在xxx位置
- git clone https://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@github.com/xiaoyuJane/leetcode.git
- git remote set-url origin git+ssh://git@github.com/xiaoyuJane/leetcode.git
     
      
     
### 设置每次提交记录的用户名和密码
 - git config --global user.email "errorl@126.com"  //git commit 命令会记录提交者的信息，所以使用git前必须先添加两条信息
 - git config --global user.name "xiaoyu_zhan"
      
     
      
### 使用main代替master
refer：https://www.jianshu.com/p/fd61cda2a6e6

git pull origin master 》》 git pull origin main
**如需要将已有repos的master换为main，可依照以下步骤：**
- git branch -m master main //重命名本地分支
- git checkout main
- git push -u origin main //重命名远程分支
- git push origin --delete master //删除远程分支
          
     
### 将本地文件夹添加到git仓库
- git init //（先进入项目文件夹）通过命令 git init 把这个目录变成git可以管理的仓库
- git add . //把文件添加到版本库中，使用命令 git add .添加到暂存区里面去，不要忘记后面的小数点“.”，意为添加文件夹下的所有文件
- git commit -m "comment ...."  // 用命令 git commit告诉Git，把文件提交到仓库。引号内为提交说明
- git remote add origin url //关联到远程库
     like "git remote add origin https://github.com/xiaoyuJane/leetcode.git"
- git pull --rebase origin master //获取远程库与本地同步合并（如果远程库不为空必须做这一步，否则后面的提交会失败）
- git push -u origin master //把本地库的内容推送到远程，使用 git push命令，实际上是把当前分支master推送到远程。执行此命令后会要求输入用户名、密码，验证通过后即开始上传。
  
  
### git 提交
- git status //查看git状态
- git add . //提交文件至本地 git 缓存区
- git add src/componet/xx.vue  //提交某个文件至本地 git 缓存区
- git commit -m 'new features' //提交代码至本地git库
- git pull //拉分支
- git push  //上传代码
     
### idea 使用git
- 本地安装了git之后，idea中就会有相关git配置
- 可以选择新建文件的时候自动add
- 然后就是git commit了，记得自动选择git and push
