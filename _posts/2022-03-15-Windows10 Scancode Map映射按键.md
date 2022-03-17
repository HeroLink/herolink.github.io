---
categories:
  - Others
tags:
  - Windows
---

# 将Scoll Lock映射为Caps Lock，将Caps Lock映射为Escape

[ Scan code mapper for keyboards](https://docs.microsoft.com/en-us/windows-hardware/drivers/hid/keyboard-and-mouse-class-drivers#scan-code-mapper-for-keyboards)

| Start offset (in bytes) | Size (in bytes) | Data                         |
| :---------------------- | :-------------- | :--------------------------- |
| 0                       | 4               | Header: Version Information  |
| 4                       | 4               | Header: Flags                |
| 8                       | 4               | Header: Number of Mappings   |
| 12                      | 4               | Individual Mapping           |
| ...                     | ...             | ...                          |
| Last 4 bytes            | 4               | Null Terminator (0x00000000) |

1. 4字节版信息，全 0
2. 4字节标志，全0
3. 4字节映射数量，`0x 00 00 00 03 `映射数量为3，低字节写高地址，写为`03 00 00 00`
4. ...，`00 3a` Caps Lock，`00 46` Scroll Lock，`00 01` Escape，写法同3
    * `3a 00 46 00` Scroll Lock映射为Caps Lock
    * `01 00 3a 00` Caps Lock映射为Escape
5. 4字节终止，全0

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Keyboard Layout]
"Scancode Map"=hex:00,00,00,00,00,00,00,00,03,00,00,00,3a,00,46,00,01,00,3a,00,00,00,00,00
```

6. 其他键位查询，[下载](https://download.microsoft.com/download/1/6/1/161ba512-40e2-4cc9-843a-923143f3456c/scancode.doc)，章节Scan Code Table

其他方法还可以使用[Power Toy](https://docs.microsoft.com/en-us/windows/powertoys/)完成映射