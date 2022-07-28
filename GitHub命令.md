# Git命令



[toc]



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