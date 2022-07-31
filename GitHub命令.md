# Git命令



[toc]



相关教程：
[Git 教程](https://www.runoob.com/git/git-tutorial.html)

相关视频：
[【尚硅谷】Git与GitHub基础全套完整版教程（快速上手，一套搞定）](https://www.bilibili.com/video/BV1pW411A7a5)
[【保姆教程】小白团队如何通过Github进行协作开发](https://www.bilibili.com/video/BV1df4y1m7B1)

![](D:\Notes\GitHub\img\Git常用命令流程图.png)

![](D:\Notes\GitHub\img\Git工作区、暂存区和版本库.png)

![](D:\Notes\GitHub\img\Git基本操作.png)



## 连接GitHub

### 方法一：HTTPS

```
git remote add origin https://github.com/<用户名>/<仓库名>.git
```

使用push命令后会弹出相应的窗口，登入GitHub账号



### 方法二：个人访问令牌

相关文章：
[【Github】remote: Support for password authentication was removed on August 13, 2021.](https://blog.csdn.net/Joy_Cheung666/article/details/119832970)

在GitHub上生成个人访问令牌后，使用命令：

```
git remote set-url origin  https://<个人访问令牌>@github.com/<用户名>/<仓库名>.git
```



### 方法三：SSH

```
git remote add origin git@github.com:<用户名>/<仓库名>.git
```

相关视频：
[如何设置GitHub SSH免密验证](https://www.bilibili.com/video/BV1NL411x7z9)



## 团队协作

相关视频：
[【保姆教程】小白团队如何通过Github进行协作开发](https://www.bilibili.com/video/BV1df4y1m7B1)



主分支：master
其他分支：branch1、branch2



### 1. 创建本地仓库

```
git init
git remote add <别名> https://github.com/<用户名>/<仓库名>
```

<别名>：origin



### 2. 第一次提交、推送（在master下）

```
git add .
git commit -m "<注释>"
git push origin master
```



### 3. 新建一个分支branch1进行开发

新建一个分支branch1并切换到该分支下：

```
git checkout -b branch1
```

提交、推送：

```
git add .
git commit -m "<注释>"
git push origin branch1
```



### 4. 将branch1与master合并

切换到master下：

```
git checkout master
```

拉取最新的master：

```
git pull origin master
```

将master与branch1合并（如果有无法自动解决的冲突，需要手动解决）：

```
git merge branch1
```

推送：

```
git push origin master
```



### 5. 将branch1与master合并

（如果需要将branch1与最新的master保持一致）

切换到master下并拉取最新的master：

```
git checkout master
git pull origin master
```

切换到branch1下：

```
git checkout branch1
```

将branch1与master合并（如果有无法自动解决的冲突，需要手动解决）：

```
git merge master
```

推送：

```
git push origin branch1
```



### 6. 其他成员新建一个分支branch2进行开发

（其他成员在其电脑本地）克隆远程仓库：

```
git clone https://github.com/<用户名>/<仓库名>
git remote add <别名> https://github.com/<用户名>/<仓库名>
```

<别名>：origin

新建一个分支branch2并切换到该分支下：

```
git checkout -b branch2
```

提交、推送：

```
git add .
git commit -m "<注释>"
git push origin branch2
```

切换到master下并拉取最新的master：

```
git checkout master
git pull origin master
```

将master与branch2合并（如果有无法自动解决的冲突，需要手动解决）：

```
git merge branch2
```

推送：

```
git push origin master
```

如果需要将branch2与最新的master保持一致，可参照5将branch2与master合并