`adb connect 127.0.0.1:58526`  连接到子系统
`adb devices`  查看当前所连接的设备
`adb kill-server`  关闭子系统
`adb push [File] /storage/emulated/0/Download/`  将本机文件复制到子系统的`Download`目录下
`adb install [*.apk]`  安装apk