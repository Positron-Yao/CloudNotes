[Windows Terminal 主题美化 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/352882990)

---

安装scoop

```powershell
Set-ExecutionPolicy RemoteSigned -scope CurrentUser
Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')
::或: Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://cdn.yulinyige.com/script/scoop-installs.ps1')
```

安装美化工具

```powershell
Install-Module posh-git
Install-Module oh-my-posh
```

配置启动文件

```powershell
code $PROFILE
```

```powershell
Import-Module posh-git
Import-Module oh-my-posh
oh-my-posh init pwsh --config "C:\Users\76923\AppData\Local\Programs\oh-my-posh\themes\powerlevel10k_mine.json" | Invoke-Expression
cls
```

前两行为导入模块，第三行为加载`powerlevel10k_mine`主题（魔改过的）

[Nerd Fonts字体下载](https://www.nerdfonts.com/font-downloads)

