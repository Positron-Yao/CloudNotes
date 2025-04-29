### 安装

<kbd>win</kbd>+<kbd>q</kbd>，搜索 启用或关闭 Windows 功能，启用wsl功能 与 虚拟机功能。

在 终端管理员 中运行:

```batch
wsl --install
```

会显示可安装的Linux发行版，以Ubuntu为例: 

```batch
wsl --install -d Ubuntu
```

安装完会自动打开Ubuntu终端，注册用户名与密码，设置初始root密码:

```bash
sudo passwd
```

---

### 图形界面

(算了不想写这个)

---

### 系统盘映射

Linux的系统文件位置在`\\wsl$`，打开这个路径后可以将其中的Ubuntu文件夹 映射网络驱动器，存到 此电脑 位置。

---

### 安装软件

```bash
sudo apt install gcc
```



