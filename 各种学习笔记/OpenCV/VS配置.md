开放简历，启动(`#include <opencv2/opencv.hpp>`)

属性 - VC++目录 - 包含目录:

```
D:\opencv\opencv\build\include
D:\opencv\opencv\build\include\opencv2
```

库目录:

```
D:\opencv\opencv\build\x64\vc16\lib
```

链接器 - 输入 - 附加依赖项:

```
// 两个opencv_world***.lib
// opencv_world490.lib
opencv_world490d.lib (有d意思是Debug)
```

之后再要配置就去扒一个 [`vs_opencv490_x64_Debug.props`](D:\opencv\) 

或者(): 

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup>
    <_PropertySheetDisplayName>vs_opencv490_x64_Debug</_PropertySheetDisplayName>
    <IncludePath>D:\opencv\opencv\build\include;D:\opencv\opencv\build\include\opencv2;$(IncludePath)</IncludePath>
    <LibraryPath>D:\opencv\opencv\build\x64\vc16\lib;$(LibraryPath)</LibraryPath>
  </PropertyGroup>
  <ItemDefinitionGroup>
    <Link>
      <AdditionalDependencies>opencv_world490d.lib;%(AdditionalDependencies)</AdditionalDependencies>
    </Link>
  </ItemDefinitionGroup>
  <ItemGroup />
</Project>
```

也彳亍()

