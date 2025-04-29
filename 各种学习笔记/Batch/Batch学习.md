``explorer`` : 打开网页
``start`` : = win+r
``del`` : 删除
``md`` : 新建文件夹
``rd`` : 删除文件夹
``copy`` : 复制文件
``ren`` : 重命名文件
``call`` : 执行另一个 .bat 文件
``attrib`` : 

- +/- : 添加/清除属性
- r = 只读，a = 存档，s =  系统，h = 隐藏


---
## for

简单用: 
```batch
@echo off
for %%a in (*.txt) do (
echo %%a
)
```
PS: 终端用 ``%a`` ，文件里用 ``%%a`` .

### 参数

- /D : ``in( )`` 内为文件夹时用这个
- /R : 进入文件夹遍历查找
- /L : ``in (set)`` 内为数字时用，``(起始值, 步长, 结束值)``  
  ! : 包含结束值
- /F : 处理字符串
  只会这样用: 
```batch
@echo off
for /f %%a in ('dir *.bat /b') do echo %%a
```
  即，获取 ``dir *.bat /b`` 返回的文件列表并接着执行后面.