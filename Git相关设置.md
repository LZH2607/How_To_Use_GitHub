# Git相关设置



[toc]



## 文件权限

相关链接：[成功解决：fatal: detected dubious ownership in repository at ‘E:/workspace/CSMarket‘。如何使用git工具通过命令行的形式](https://blog.51cto.com/u_15740728/5805813)

```
git config --global --add safe.directory "*";
```



## 显示中文

相关链接：[git 显示中文和解决中文乱码](https://zhuanlan.zhihu.com/p/133706032)

```
git config --global core.quotepath false
```

在Git Bash界面右击 > Options > Text，Locale选择zh_CN，Character set选择UTF-8

