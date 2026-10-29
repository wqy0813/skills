# skills

wqy0813 的个人 Agent Skills 合集，用于保存和持续改进学习、笔记与日常工作中可复用的流程。

当前可安装的技能包是 [`leetcode-notes/`](https://github.com/wqy0813/skills/tree/main/leetcode-notes)。其中的 [`leetcode-notes/SKILL.md`](https://github.com/wqy0813/skills/blob/main/leetcode-notes/SKILL.md) 是给 Agent 读取的说明文件。安装时需要保留整个技能目录，包括 `references/` 和 `agents/`。

**第一次使用：把下方“安装到 Codex”里的整段请求复制给 Codex，明确指定要安装的仓库和子目录。**

`leetcode-notes` 的[写作结构](./leetcode-notes/references/note-template.md)和[交互配色](./leetcode-notes/references/datacore-guide.md)均随包提供，不需要预先准备样板笔记。

## 技能索引

| 技能包目录 | 说明入口 | 适用场景 |
| --- | --- | --- |
| [leetcode-notes](./leetcode-notes/) | [SKILL.md](./leetcode-notes/SKILL.md) | 按灵茶山艾府题单整理中文 Obsidian 刷题笔记，包含 Datacore 演示、通用模板与个人答疑 |

## 安装到 Codex

### 方法一：把下面整段请求复制给 Codex

适用于有本地文件写入和 GitHub 下载能力的 Codex 环境。

```text
请使用 $skill-installer 安装以下 GitHub 技能：
仓库：https://github.com/wqy0813/skills
分支：main
技能目录：leetcode-notes
技能目录地址：https://github.com/wqy0813/skills/tree/main/leetcode-notes

请下载并安装完整的 leetcode-notes 文件夹，保留 SKILL.md、references/ 和 agents/，
使用当前 Codex 环境支持的用户级技能安装位置。
安装后检查文件是否齐全，并告诉我实际安装路径与识别情况。
如果下载或写入失败，请报告具体错误。
```

这里已经明确了仓库 `wqy0813/skills`、分支 `main` 和仓库内路径 `leetcode-notes`，Codex 可据此定位安装内容。OpenAI 官方文档支持使用 `$skill-installer` 从其他仓库下载技能；安装后通常会自动识别，未出现时可重启 Codex。[官方说明](https://learn.chatgpt.com/docs/build-skills#install-curated-skills-for-local-use)

### 方法二：Skills CLI

已安装 Node.js 的用户也可以使用 [Skills CLI](https://github.com/vercel-labs/skills)：

```bash
npx skills add wqy0813/skills --skill leetcode-notes
```

按提示选择目标 Agent 和安装范围。

### 方法三：手动复制完整技能目录

克隆仓库：

```bash
git clone https://github.com/wqy0813/skills.git
```

从克隆结果中取出 `leetcode-notes/`，将整个文件夹复制到 Codex 支持的技能目录。当前官方文档列出的用户级目录为 `$HOME/.agents/skills/`，项目级目录为 `.agents/skills/`；使用内置安装器时按其当前环境配置的目标位置安装。[目录说明](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills)

复制后保留以下结构，避免多套一层仓库目录或遗漏参考文件：

```text
<技能目录>/
└── leetcode-notes/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── references/
        ├── note-template.md
        ├── topic-sources.md
        └── datacore-guide.md
```

## 安装后使用

```text
使用 $leetcode-notes，帮我整理网格图 DFS 小专题笔记，保存到我指定的 Obsidian 目录。
```

技能安装和 Obsidian 插件配置分别处理：笔记里的交互展示使用 Datacore，需要在目标 Obsidian 库中启用相应插件与 JavaScript 视图。

## 找不到入口时

- **仓库根目录没有 `SKILL.md`**：本仓库是技能合集，当前技能说明在 [`leetcode-notes/SKILL.md`](https://github.com/wqy0813/skills/blob/main/leetcode-notes/SKILL.md)，完整安装目录在 [`leetcode-notes/`](https://github.com/wqy0813/skills/tree/main/leetcode-notes)。
- **只下载了一个说明文件**：补齐同目录下的 `references/` 和 `agents/`，保持上面的结构。
- **已下载但 Codex 没有识别**：核对实际安装目录与 `SKILL.md`，避免把整个 `skills` 仓库当作一个技能目录；必要时重启 Codex。
- **Codex 报网络或权限错误**：按实际错误处理下载或写入条件；仅贴仓库链接无法保证安装成功。

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
