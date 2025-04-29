```batch
Function Get-Icon {
    [CmdletBinding()]
    Param (
        [Parameter(Mandatory=$True, HelpMessage="C:\Users\76923\Desktop")]
        [string]$folder
    )

    [System.Reflection.Assembly]::LoadWithPartialName('System.Drawing') | Out-Null

    md $folder -ea 0 | Out-Null

    dir $folder *.exe -ea 0 -rec |
    ForEach-Object {
        $baseName = [System.IO.Path]::GetFileNameWithoutExtension($_.FullName)
        Write-Progress "正在提取图标" $basename
        [System.Drawing.Icon]::ExtractAssociatedIcon($_.FullName).ToBitmap().Save("$folder\$basename.ico")
    }
}

Get-Icon -folder "C:\Users\76923\Desktop"

```

其中`"C:\Users\76923\Desktop"`更改为`.exe`文件的位置即可.