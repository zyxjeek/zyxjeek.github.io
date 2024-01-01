title: Hexon的使用
date: '2023-12-29 22:30:09'
tags:
  - 计算机工具
---
> 好久没用Hexo写博客了，笔者准备寒假时更新一波洛谷的题解，但由于用命令行写博客很不方便，于是找到了Hexon这款图形化Hexo博客部署工具（

## 1. 安装

这一步很简单，在确保自己的Hexo安装正确后，执行以下命令即可

```bash
git clone https://github.com/gethexon/hexon --depth 1
cd hexon
pnpm install
pnpm run setup
```

此时要输入Hexo博客的路径，并设置用户名、密码。

![](https://i.postimg.cc/rFB32W5P/Snipaste-2023-12-29-22-19-54.png)

## 2. 启动和使用

运行`pnpm start`,打开[服务器](http://localhost:5777),用**输出消息中的**用户名和你设置的密码（不要用你之前设的用户名，有bug）

进入主页后就可以新建管理文章和页面等等，可以一键部署/清理/生成，还可以在这里写文章，连md编辑器都省了。


---

其实笔者也刚刚开始使用这款工具，~~这条博客是测试用的~~，后续如果有什么更加有趣的玩法我会随时更新。


---
The END
