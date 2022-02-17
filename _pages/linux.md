---
permalink: /linux/
title: "Linux Note"
---

# tar打包

| option | meaning             |
| ------ | ------------------- |
| -c     |                     |
| -x     | 解包                |
| -f     | 指定包名            |
| -C     | 打包/解包到指定目录 |

# 查看目录中文件数量

1. 不包含子目录中的文件数量， `ls -l [dir] | grep "^-" | wc -l`
2. 包含子目录中的文件 数量，`ls -lR [dir] | grep "^-" | wc -l`
3. 目录中的文件夹数量，不含子目录，`ls -l [dir] | grep "^d" | wc -l`
4. 目录中的文件夹数量，包含子目录，`ls -lR [dir] | grep "^d" | wc -l`
5. `-R, --recursive list subdirectories recursively`
2. `^-` 匹配文件，`^d` 匹配目录

3. `man wc` print newline, word, and byte counts for each file
4. `wc -l` 统计输出信息的行数

