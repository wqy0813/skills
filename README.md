# skills

wqy0813 的个人 Agent Skills 合集，用于保存和持续改进学习、笔记与日常工作中可复用的流程。

每个 Skill 独立存放，以 `SKILL.md` 为入口；较详细的模板和规则放在 `references/`，按需读取。

`leetcode-notes` 的[写作结构](./leetcode-notes/references/note-template.md)和[交互配色](./leetcode-notes/references/datacore-guide.md)均随包提供，不需要预先准备样板笔记。

## 技能索引

| Skill | 适用场景 | 主要产出 |
| --- | --- | --- |
| [leetcode-notes](./leetcode-notes/) | 按灵茶山艾府题单整理刷题笔记、学习算法小专题、复盘个人疑问 | 中文 Obsidian Markdown 笔记，包含 Datacore 核心演示、通用模板、代表题变化与个人答疑 |

## 快速使用

使用 [Skills CLI](https://github.com/vercel-labs/skills) 安装所需技能：

```bash
npx skills add wqy0813/skills --skill leetcode-notes
```

按命令提示选择目标 Agent 和安装范围。也可以克隆仓库，将所需 Skill 的完整目录复制到所用 Agent 的技能目录，保留其中的参考文档。

```bash
git clone https://github.com/wqy0813/skills.git
```

安装后，可在支持技能调用的 Agent 中使用：

```text
使用 $leetcode-notes，帮我整理网格图 DFS 小专题笔记，保存到指定的 Obsidian 目录。
```

## leetcode-notes

按“章节目录 → 小专题笔记 → 代表题”组织，主要参考灵茶山艾府的算法题单与题解。笔记的阅读顺序是：

1. 一句话抓住核心主线。
2. 通过 Datacore 交互与小例子理解方法。
3. 提炼可复用的代码模板。
4. 用具体题目说明相对模板的变化。
5. 整理真实疑问、易错清单、相关笔记与复杂度。

具体题解会先确认采用灵神优化解法还是用户自己的解法。公共疑问集中讲，题目特有的卡点保留在题内；代码、解释与验证情况按实际材料记录。

笔记使用普通 Obsidian `.md` 文件，交互部分使用 Datacore。用户可以指定自己的保存目录和参考笔记；核心写法与配色已整理到技能包中，无需取得作者的个人笔记库。

## 仓库结构

```text
skills/
├── README.md
├── .gitignore
├── .gitattributes
└── leetcode-notes/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── references/
        ├── note-template.md
        ├── topic-sources.md
        └── datacore-guide.md
```

## 新增与维护

在仓库顶层创建与 Skill 名称一致的目录，至少包含带 `name` 和 `description` 的 `SKILL.md`。需要时再增加 `references/`、`scripts/` 或 `assets/`，并更新技能索引。

修改一个 Skill 时，同步检查其参考文档、示例和内部链接。结构检查通过与真实使用效果分开记录；新脚本和交互组件按实际情况验证。

## 参考与致谢

- [HOWILLMAKEIT/skills](https://github.com/HOWILLMAKEIT/skills)：参考其个人技能合集的目录组织和使用说明形式。
- [灵茶山艾府 / EndlessCheng](https://github.com/EndlessCheng)：算法题单与题解的主要来源，具体笔记应链接实际使用的原文。
- [amanattar/leetcode-helper](https://github.com/amanattar/leetcode-helper)、[2083423138wyfff/leetcode](https://github.com/2083423138wyfff/leetcode)：`leetcode-notes` 最初融合的题解结构、逐步引导与复盘方法。
- [Datacore](https://github.com/blacksmithgu/datacore)：Obsidian 内的交互视图支持。
