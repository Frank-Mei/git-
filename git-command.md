### 1.创建版本库
```
git init
```

### 2.文件添加到git库的暂存区（stage）
```
 git add test.txt
```

### 3.把暂存区的所有修改提交到git版本库
```
git commit -m “注释说明"
```

### 4.查看仓库当前的状态
```
git status
```

### 5.查看difference
```
git diff
```

### 6.查看log 

```
git log
```
*git log命令显示从最近到最远的提交日志，我们可以看到3次提交。 如果嫌输出信息太多，看得眼花缭乱的，可以加上--pretty=oneline参数：*

```
git log --pretty=oneline
```

### 7.版本回退
#### Git必须知道当前版本是哪个版本，在Git中，用HEAD表示当前版本，上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100。
```
git reset --hard HEAD^
```
#### 指定回到某个版本
```
git reset --hard 0d3070c
```

### 8.查询每一次版本
```
git reflog
```

### 9.撤销修改
```
git checkout -- test3.txt
```
*命令git checkout -- test3.txt意思就是，把test3.txt文件在工作区的修改全部撤销，这里有两种情况：*
*一种是test3.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；*
*一种是test3.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。*
*总之，就是让这个文件回到最近一次git commit或git add时的状态*

### 10.删除
```
git rm test.txt
```

### 11.gitLab创建SSH Keys
#### 在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：
```
ssh-keygen -t rsa -C "zhangsan@163.com"
```
*第1步：创建SSH Key。在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，id_rsa.pub是公钥*
*第2步：登陆GitLab，，“SSH Keys”页面：*
*点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容*

### 12.提交到远程仓库
#### 第一次提交
```
git config --global user.name "username"
git config --global user.email "username@163.com"
git push -u origin master
```
#### 之后提交
```
git push -u origin master
```
### 13.从远程仓库克隆
```
git clone git@192.168.18.14:h5/git_test.git
```
### 14.创建并切换分支
```
git checkout -b dev
```
### 15.从远程仓库克隆
```
git clone git@address/git_test.git
```

### 16.创建并切换分支
```
git checkout -b dev
```
*git checkout命令加上-b参数表示创建并切换，相当于以下两条命令：*
```
git branch dev
git checkout dev
```

### 17.查看分支
#### 查看本地分支
```
git branch
```
#### 查看远程分支
```
git branch -a
```

### 18.合并某分支到当前分支
```
git merge dev
```

### 19.删除分支
#### 删除本地分支
```
git branch -d dev
```

#### 删除远程分支
```
git push origin --delete <branchName>
```
#### 强行删除分支
```
git branch -D dev
```

### 20.把当前工作现场“储藏”起来，等以后恢复现场后继续工作
```
git stash
```
*git stash list命令可以查看隐藏的工作现场*
```
git stash list
```
### 21.推送分支
```
git push origin dev
```
### 22.从远程获取最新版本到本地，不会自动merge
```
git fetch origin master
```
### 23.从远程获取最新版本并merge到本地
```
git pull origin master
````