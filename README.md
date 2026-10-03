# make-knowledge-cards

`make-knowledge-cards` 是一个 Codex Skill，用于把文章整理成简洁、聚焦且忠于原文的知识卡片。

## 项目解决什么问题

长文章通常混有铺垫、重复表述和次要细节，直接复习不易抓住重点。本项目帮助用户从文章中提取真正重要且彼此独立的知识点，并转换成便于理解和自测的卡片，同时避免加入原文没有的信息。

## 主要功能

- 接受用户直接粘贴的文章。
- 读取本地 `.md`、`.markdown` 和 `.txt` 文件。
- 在内容充足时生成 5～8 张知识卡片；信息不足时减少数量，不强行凑数。
- 每张卡片只讲一个知识点，包含标题、核心知识、简明解释，以及原文中的例子或可由原文回答的自测问题。
- 优先保留主要观点、关键概念、机制、区别和可复用原则。
- 合并重复内容，保留原文中的观点归属、限定条件和不确定性。
- 默认使用原文语言，也可以按用户指定的语言输出。

本项目暂不支持网页抓取、PDF、Anki 导出和图形界面。

## 安装方法

Skill 的实际目录是 `skills/make-knowledge-cards`。将这个目录复制到 Codex 能发现的 Skill 目录即可。

安装到当前仓库，仅在该仓库中使用：

```powershell
New-Item -ItemType Directory -Force .codex\skills | Out-Null
Copy-Item -Recurse -Force skills\make-knowledge-cards .codex\skills
```

安装到当前用户的 Codex 配置中，供不同项目使用：

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.codex\skills" | Out-Null
Copy-Item -Recurse -Force skills\make-knowledge-cards "$env:USERPROFILE\.codex\skills"
```

如果目标目录已经存在，请先确认其中是否有需要保留的修改；上述命令不会主动清理旧文件。

## 使用方法

直接粘贴文章：

```text
使用 $make-knowledge-cards，把下面的文章转换成知识卡片：

<粘贴文章内容>
```

处理本地文件：

```text
使用 $make-knowledge-cards，把 notes/article.md 转换成知识卡片。
```

也可以明确指定输出语言：

```text
使用 $make-knowledge-cards，读取 notes/article.txt，并用中文生成知识卡片。
```

## 输入输出示例

输入：

```text
间隔学习把复习安排在逐渐拉长的时间间隔上。相比把复习集中在一次完成，这种做法能让学习者在即将遗忘时重新提取信息。主动回忆是指在不查看答案的情况下尝试想起内容；它比单纯重读更能检验是否真正掌握。
```

输出（原文只有两个独立知识点，因此不强行生成 5 张）：

```markdown
## 卡片 1：间隔学习

**核心知识：** 间隔学习把复习分散到逐渐拉长的时间间隔中。

**简明解释：** 它让学习者在接近遗忘时再次提取信息，而不是一次集中复习。

**自测问题：** 间隔学习与集中复习在时间安排上有什么不同？

## 卡片 2：主动回忆

**核心知识：** 主动回忆是在不查看答案时尝试想起学习内容。

**简明解释：** 与单纯重读相比，它更能暴露学习者是否真正掌握了内容。

**自测问题：** 为什么不看答案进行回忆能用于检验掌握程度？
```
