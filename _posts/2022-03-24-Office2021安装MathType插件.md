---
categories:
  - Computer Science
  - Others
tags:
  - Tool
---

# Office2021安装MathType插件

1. MathType版本7.4.8
2. Offcie2021版本LTSC 2202 64bit

## Word

操作，根据64/32bit决定，此处为64bit，MathType安装路径依情况而定

* `E:\Program Files (x86)\MathType\MathPage\64\MathPage.will` 移动到 `C:\Program Files\Microsoft Office\root\Office16` 目录下
* `E:\Program Files (x86)\MathType\Office Support\64\MathType Commands 2016.dotm` 移动到 `C:\Program Files\Microsoft Office\root\Office16\STARTUP` 目录下
* Word -> File -> Options -> Trust Center -> Trust Center Settings -> Trusted Locations -> Add new location
    * Path: `C:\Program Files\Microsoft Office\root\Office16\STARTUP\`
    * Description (Optional): `MathType`

* 重启Word即可

## Powerpoint

* `E:\Program Files (x86)\MathType\Office Support\64\MathType AddIn (PowerPoint 2016).ppam` 移动到 `C:\Users\[username]\AppData\Roaming\Microsoft\AddIns` 目录下，username依情况而定
* Powerpoint -> Options -> Add-ins -> Manage -> Powerpoint Add-ins -> Go -> Add New -> 选择刚刚复制的文件
* 重启Powerpoint即可