创建版本库

```git
git init
```

添加到暂存区

```git
git add readme.txt
git add .
```

提交更改

```git
git commit -m "wrote a readme file"
```

关联仓库

```git
git remote add origin git@github.com:michaelliao/learngit.git
```

本地库的所有内容推送到远程库上

```git
 git push -u origin master
```

之后提交只需要

```git
git push origin master
```

