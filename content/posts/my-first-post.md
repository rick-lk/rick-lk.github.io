---
title: "我的第一篇文章"
date: 2026-03-01T18:55:00+08:00
draft: false
buildDrafts : true  
tags: ["Hugo", "Blog"]
categories: ["Tech"]
---
draft: false  # <--- 重要：发布前改为 false，或者在配置中设置；井号后要删除否则会发布失败 

这里是文章内容，支持 Markdown 语法。

这个错误非常具体且容易修复！🎉

🚨 错误分析
报错信息：
failed to unmarshal YAML: yaml: line 2: did not find expected key
位置：content/posts/test.md:2:1 (第 2 行，第 1 列)

原因：你的文章 test.md 的 YAML Front Matter（头部信息）格式写错了。
通常是因为：
缺少结束符：只有开头的 ---，没有结尾的 ---。
缩进错误：YAML 对缩进非常敏感，key 前面不能有空格。
冒号后缺少空格：YAML 要求 key: value 的冒号后面必须有一个空格。
特殊字符未加引号：标题里有冒号或特殊符号没加引号。

✅ 解决方案：修复 test.md 文件

请在 Codespaces 中打开 content/posts/test.md 文件，检查并修正它的头部。

❌ 错误的写法示例 (可能导致报错)

title:我的测试文章  # 错误：冒号后没空格
date: 2026-03-02
draft: false
错误：缺少底部的 ---
这里开始写正文...

或者：

title: "My Test: A Story" # 如果标题里有冒号，最好加引号，虽然通常没问题
 date: 2026-03-02        # 错误：date 前面多了一个空格
draft: false

✅ 正确的写法模板
请确保你的文件头部严格长这样（注意空格和两个 ---）：

title: "我的测试文章"
date: 2026-03-02T19:52:00+08:00
draft: false
tags: ["test", "hugo"]
categories: ["Tech"]

这里是文章的正文内容...

关键检查点：
第一行必须是 --- (三个减号)。
最后一行（头部结束处）也必须是 ---。
键值对格式：key: value (冒号后面必须有一个空格)。
无多余缩进：title, date 等关键词必须顶格写，前面不能有空格。
标题引号：如果标题里包含冒号 :、引号 ' 等特殊字符，建议用双引号把标题包起来，如 title: "My Title: Subtitle"。

🚀 操作步骤

在 Codespaces 中编辑 content/posts/test.md。
修正格式，确保符合上面的“正确写法”。
保存文件。
提交并推送：
        git add .
    git commit -m "fix: correct YAML front matter in test.md"
    git push
    
去 GitHub Actions 查看新的构建，这次应该就能成功了！

如果不确定哪里错了，你可以把 test.md 文件的前 10 行内容复制发给我，我帮你具体指出哪一行有问题。