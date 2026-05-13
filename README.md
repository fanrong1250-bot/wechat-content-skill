# wechat-content-skill
把一句话需求变成一篇 6000 字、有观点、有反转、不像 AI 写的公众号深度文章。

一个 Claude Skill —— 让 Claude 不再写出那种"看着对、读着空"的稿子。

这是什么
wechat-content-skill 是一个 Claude Skill，安装后 Claude 在你写公众号深度长文时会自动加载。

它的核心不是"代写"，是把"AI 写作"的几个老毛病按死：

观点没有敌人 → 强制要求"会有人不同意"的核心论点
没有反转 → 必须有"你以为 X，其实 Y"的结构
平衡客观到失去立场 → 敢下判断，不"辩证看待"
翻译腔 / 引导腔 / 总结腔 / 升华腔 → 全部明确禁用
数据堆砌 → 每篇统计数据段落 ≤ 4 个
纯文字交付 → 强制配 2-3 张离线 HTML 图表
适合：想用 Claude 系统化写公众号、长博客、观点性长文的人。
不适合：写朋友圈短文案、纯技术文档、新闻稿。

工作流（强制四步，跳一步都不行）
1. 背景检索    (静默)  Claude 自己搜 2-4 次，找数据点、对立观点、反转角度
        ↓
2. 需求澄清    Claude 基于检索结果给你 3 个具体方向选项（不会问"你想写啥"这种废话）
        ↓
3. 大纲确认    输出 1 个最优大纲 + 2-3 个备选反转角度 + 3 个标题候选
              你不说"开始写"，绝不动笔
        ↓
4. 落盘成文    ~6000 字写入 articles/{文件名}.md
              图表 HTML 写入 articles/配图/{文件名}.html（纯离线，双击可看）
每一步都有明确的输入输出，不会一上来就给你倒一大盆字。

安装
Claude Code / Claude Desktop（推荐）
把仓库克隆到本地 skills 目录，注意文件夹名要改成 wechat-content-skill（和 SKILL.md 里的 name 字段对齐）：

git clone https://github.com/fanrong1250-bot/wechat-articel.git ~/.claude/skills/wechat-content-skill
只想给单个项目用，就放到项目目录下：

git clone https://github.com/fanrong1250-bot/wechat-articel.git .claude/skills/wechat-content-skill
重启 Claude Code 后，输入 /skills 应该能看到 wechat-content-skill 出现在列表里。

Claude.ai（Web，Pro / Max / Team / Enterprise 用户）
进入 Settings → Capabilities，确认 Code execution and file creation 已开启
进入 Customize → Skills
上传本仓库的 SKILL.md
在 Skills 列表里把 wechat-content-skill 开关打开
用法
安装好之后，不需要任何特殊命令。正常说话就行：

帮我写一篇关于 XX 的公众号文章
有个话题：YYY，想写成长文，5000 字以上
写篇深度分析：ZZZ 这件事到底意味着什么
Claude 会自动识别触发，进入四步流程。整个过程它会主动问你方向，给你大纲让你改，确认之后才落笔。

输出结构
