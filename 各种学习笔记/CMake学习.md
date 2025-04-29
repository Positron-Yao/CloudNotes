### 安装

```bash
sudo apt install cmake
```

---

### 基本使用

CMakeLists.txt:

```cmake
cmake_minimum_required (VERSION 2.8)	# 确定cmake的最低版本号

project (demo)		# 工程名

add_executable(test main.c)		# 生成文件 及使用到的源文件
```

之后在此文件夹的命令行中:

```bash
cmake .
make
```

---

[Linux下CMake简明教程_linux cmake-CSDN博客](https://blog.csdn.net/whahu1989/article/details/82078563)
