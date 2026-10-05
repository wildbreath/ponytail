<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.png">
    <img src="assets/logo.png" width="220" alt="Ponytail，懒惰的高级开发者">
  </picture>
</p>

<h1 align="center">Ponytail</h1>

<p align="center">
  <em>他一言不发，只写一行代码。它能用。</em>
</p>

<p align="center">
  <a href="https://trendshift.io/repositories/50668?utm_source=repository-badge&amp;utm_medium=badge&amp;utm_campaign=badge-repository-50668" target="_blank" rel="noopener noreferrer"><img src="https://trendshift.io/api/badge/repositories/50668" alt="DietrichGebert%2Fponytail | Trendshift" width="250" height="55"/></a>
</p>

<p align="center">
  <img src="https://img.shields.io/github/stars/DietrichGebert/ponytail?style=flat-square&color=111111&label=stars" alt="Stars">
  <img src="https://img.shields.io/github/v/release/DietrichGebert/ponytail?style=flat-square&color=111111&label=release" alt="Release">
  <img src="https://img.shields.io/npm/v/@dietrichgebert/ponytail?style=flat-square&color=111111&label=npm" alt="npm">
  <img src="https://img.shields.io/badge/works%20with-20%20agents-111111?style=flat-square" alt="支持 20 种智能体">
  <img src="https://img.shields.io/badge/license-MIT-111111?style=flat-square" alt="MIT 许可证">
</p>

<p align="center">
  <a href="https://trendshift.io/repositories/50668" target="_blank" rel="noopener noreferrer"><img src="https://trendshift.io/api/badge/trendshift/repositories/50668/daily" alt="DietrichGebert/ponytail | Trendshift" width="250" height="55"/></a>
  <a href="https://trendshift.io/repositories/50668" target="_blank" rel="noopener noreferrer"><img src="https://trendshift.io/api/badge/trendshift/repositories/50668/weekly" alt="DietrichGebert/ponytail | Trendshift" width="250" height="55"/></a>
  <a href="https://trendshift.io/repositories/50668?utm_source=trendshift-badge&amp;utm_medium=badge&amp;utm_campaign=badge-trendshift-50668" target="_blank" rel="noopener noreferrer"><img src="https://trendshift.io/api/badge/trendshift/repositories/50668/monthly?language=JavaScript" alt="DietrichGebert%2Fponytail | Trendshift 月榜" width="250" height="55"/></a>
</p>

<p align="center">
  <strong>代码量减少约 54%（最高 94%）&middot; 成本降低约 20% &middot; 速度提升约 27% &middot; 安全性 100%</strong><br>
  <sub>数据来自真实 Claude Code 会话：同一智能体在一个真实开源项目（FastAPI + React）中，有无本技能时的对比。约 54% 是 12 项功能任务的平均值（Haiku 4.5，n=4）；遇到智能体容易过度实现的任务（例如日期选择器）时最高可达 94%，代码本就精简时则接近于零。ponytail 保留了全部安全防护，而单纯要求“写成一行”的提示会漏掉一项。（早期单轮基准将 80–94% 作为统一结果；与公平的智能体基线相比，它其实是单项任务的上限，而非平均值。）<a href="benchmarks/results/2026-06-18-agentic.md">完整报告</a> &middot; <a href="benchmarks/">复现实验</a>。</sub>
</p>

<p align="center">
  <sub><a href="README.md">English</a> &middot; <a href="README.es.md">Español</a> &middot; <a href="README.ko.md">한국어</a></sub>
</p>

---

<p align="center">
  <a href="https://ponytail.dev/soon"><img src="assets/waitlist-banner.png" alt="新东西正在路上，加入候补名单" width="760"></a>
</p>

## 已有项目使用 Ponytail 构建

<a href="https://theretriever.app">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/retriever-logo-dark.svg">
    <img src="assets/retriever-logo-light.svg" height="128" alt="Retriever">
  </picture>
</a>

---

你认识这种人。扎着长马尾，戴着椭圆眼镜，在公司的资历比版本控制还老。你拿五十行代码给他看；他一言不发，把它改成了一行。

Ponytail 把他装进你的 AI 智能体。

## 前后对比

你要一个日期选择器。智能体装上 flatpickr，写个包装组件，加一份样式表，然后开始讨论时区。

用了 ponytail：

```html
<!-- ponytail: 浏览器自带 -->
<input type="date">
```

更多幸存案例见 [examples/](examples/)。

## 数据

诚实的测量方式，是让真实智能体完成真实工作：运行一个无界面的 Claude Code 会话，编辑 [tiangolo 的 full-stack-fastapi-template](https://github.com/fastapi/full-stack-fastapi-template)（真实的 FastAPI + React 仓库），然后根据它留下的 `git diff` 评分。12 个功能任务，同一智能体分别在启用和未启用技能时执行，n=4，模型为 Haiku 4.5。

<p align="center">
  <img src="assets/benchmark-agentic.svg" width="860" alt="各实验组相对于无技能基线的代码行数、token、成本和耗时百分比（Haiku 4.5）。ponytail 在所有指标中最低：代码行数 46%、token 78%、成本 80%、耗时 73%；caveman 的 token、成本和耗时超过 100%；yagni-oneliner 的代码行数为 67%。另设对抗性安全测试：基线、caveman 和 ponytail 均为 100%，yagni-oneliner 为 95%。">
</p>

| 相比无技能基线 | 代码行数 | token | 成本 | 耗时 | 安全性 |
|---|--:|--:|--:|--:|--:|
| **ponytail** | **-54%** | **-22%** | **-20%** | **-27%** | **100%** |
| caveman（精简表达对照组） | -20% | +7% | +3% | +2% | 100% |
| “YAGNI + 单行代码”提示 | -33% | -14% | -21% | -30% | 95% |

ponytail 是唯一一组让所有指标都下降、同时保持完全安全的方案。真正存在过度实现陷阱时，缩减最明显（日期选择器从 404 行降至 23 行，颜色选择器从 287 行降至 23 行，因为它选择原生 `<input>`，而不是另造组件）；代码本就精简时，差异接近于零。完整方法、逐任务表格与限制见 [benchmarks/results/2026-06-18-agentic.md](benchmarks/results/2026-06-18-agentic.md)。

<details>
<summary><strong>早期单轮数据（独立生成）</strong></summary>

5 个日常任务，3 个模型，3 个实验组（无技能、[caveman](https://github.com/JuliusBrussee/caveman)、ponytail），各运行 10 次并报告中位数。每次只使用一个提示和一次回复，统计回复中的代码行数：

<p align="center">
  <img src="assets/benchmark-3model.svg" width="860" alt="Haiku、Sonnet 和 Opus 各实验组代码行数的中位数">
</p>

结果显示**代码量减少 80–94%**。[#126](https://github.com/DietrichGebert/ponytail/issues/126) 公允地指出，裸模型基线会在回答中加入大量说明和备选方案，因此差距部分来自对话基线本身。上面的智能体实验数据是修正后、经得住推敲的版本。运行 `npx promptfoo eval -c benchmarks/promptfooconfig.yaml` 可复现单轮实验。

</details>

**规则从来不是“token 越少越好”。** 真正的规则是：只编写任务需要的内容，绝不牺牲验证、错误处理、安全性或可访问性。代码少，是因为只保留了必要部分，而不是在玩代码高尔夫。对于遵循这套阶梯的模型，更低的成本和延迟只是副作用；如果某个精简型推理模型花费大量思考 token 反复权衡各层选择，结果也可能相反（GPT-5.5 就是如此）。

## 工作原理

写代码前，智能体会在第一个可行的层级停下：

```
1. 这东西真的需要存在吗？   → 不需要：跳过（YAGNI）
2. 代码库里已经有了吗？     → 复用，不重写
3. 标准库能完成吗？         → 用标准库
4. 平台有原生功能吗？       → 用原生功能
5. 已安装的依赖能解决吗？   → 用现有依赖
6. 能写成一行吗？           → 写成一行
7. 只有到这里：写出能用的最小实现
```

这套阶梯在*理解问题之后*才开始，而不是替代理解：智能体会先阅读变更涉及的代码，追踪完整的真实流程，再选择在哪一级停下。解决方案可以偷懒，读代码绝不偷懒。

懒惰不等于失职：信任边界的输入验证、防止数据丢失的错误处理、安全性和可访问性，从来都不能省。

## 安装

这是 ponytail 会要求你付出的最大努力：

Claude Code 和 Codex 插件（以及 Cursor hooks）会运行两个很小的 Node.js 生命周期钩子，因此 `node` 必须位于 PATH 中（Nix/nvm 用户请注意：它必须位于非交互式 shell 的 PATH 中）。如果没有，技能本身仍能工作，但每次调用钩子都会显示无害的 `node: command not found` 错误；安装 Node 或将其加入对应 PATH 即可消除。

### Claude Code

```
/plugin marketplace add DietrichGebert/ponytail
```
```
/plugin install ponytail@ponytail
```

安装时必须分两次发送以上命令。

Claude Code 桌面应用的 Code 标签页步骤相同：在提示框中输入以上两个 `/plugin` 命令；或点击旁边的 **+**，选择 **Plugins** → **Add plugin** 浏览已配置的市场。市场可在侧边栏的 **Customize** 中管理。

### Codex

```bash
codex plugin marketplace add DietrichGebert/ponytail
codex plugin add ponytail@ponytail
```

运行 `codex`，打开 `/hooks`，检查并信任其中两个生命周期钩子，然后新建一个线程。

同一安装也适用于 Codex 桌面应用；安装后重启应用即可加载插件。

### GitHub Copilot CLI

```bash
copilot plugin marketplace add DietrichGebert/ponytail
copilot plugin install ponytail@ponytail
```

在交互式 Copilot CLI 会话中，可使用对应的斜杠命令：

```
/plugin marketplace add DietrichGebert/ponytail
/plugin install ponytail@ponytail
```

Copilot CLI 会按插件名为命令添加命名空间，例如：

```text
/ponytail:ponytail ultra
/ponytail:ponytail-review
```

### Pi agent harness

```
pi install git:github.com/DietrichGebert/ponytail
```

### OpenCode

添加到 `opencode.json`：

```json
{ "plugins": ["@dietrichgebert/ponytail"] }
```

也可以从检出的仓库运行（插件会复用 `hooks/` 和 `skills/`）：

```json
{ "plugins": ["./.opencode/plugins"] }
```

它会在每轮对话中按当前级别注入规则集，并添加 `/ponytail` 命令（见[命令](#命令)）。OpenCode 也会自动加载本仓库的 `AGENTS.md`，因此即使没有插件，规则仍然生效。插件额外提供 `lite/full/ultra/off` 级别。

仅支持 OpenCode 2。`./` 路径相对于项目的 `opencode.json` 解析；若要让多个项目共用同一份检出，请指向该检出中 `.opencode/plugins` 目录的绝对路径。`plugins` 条目必须指向**目录**，不能指向文件：OpenCode 2 会拒绝指向 `ponytail.mjs` 的路径，并报错 `configured plugin path must be a directory`。直接在 OpenCode 2 中打开本仓库不需要任何配置，它会自行加载 `.opencode/plugins/index.js`。

OpenCode 1 使用旧的 `plugin` 键：`{ "plugin": ["@dietrichgebert/ponytail"] }`；从检出运行时则使用文件路径：`{ "plugin": ["./.opencode/plugins/ponytail.mjs"] }`。

### Gemini CLI

```bash
gemini extensions install https://github.com/DietrichGebert/ponytail
```

每个会话都会将规则集作为常驻上下文加载，并注册 `/ponytail` 命令；`skills/` 也会一并安装，在任务需要时激活。

Gemini 适配器有意不提供根目录下的 `hooks/hooks.json`：Gemini 会自动加载该路径，而 Ponytail 的生命周期钩子使用的是 Claude/Codex 事件名称。

### Qoder

Qoder 会自动把仓库根目录的 `AGENTS.md` 作为常驻上下文加载，因此从本仓库检出运行 ponytail 无需配置。若只想为单个项目启用规则，将 [`.qoder/rules/ponytail.md`](.qoder/rules/ponytail.md) 复制到该项目的 `.qoder/rules/`。六项 ponytail 技能（`/ponytail`、`/ponytail-review`、`/ponytail-audit`、`/ponytail-debt`、`/ponytail-gain`、`/ponytail-help`）可通过 Qoder 的 Skill 系统使用；[`.qoder-plugin/plugin.json`](.qoder-plugin/plugin.json) 中的插件清单指向 `skills/` 目录。

若要获得完整插件能力（自动激活模式，并在每个提示中注入规则集），请将 [`hooks/qoder-hooks.json`](hooks/qoder-hooks.json) 中的钩子加入 `.qoder/settings.json`，并把 `PONYTAIL_DIR` 替换为 ponytail 检出路径。Qoder 的 `UserPromptSubmit` 钩子会在首次提示时激活默认模式，并在每轮注入规则集；匹配 `task|Task` 的 `PreToolUse` 会向子智能体注入规则。级别切换（`/ponytail lite|full|ultra|off`）会自动生效。

### Antigravity CLI

Google 正在把 Gemini CLI 更名为 Antigravity CLI（可执行文件为 `agy`）；同一扩展可这样安装：

```bash
agy plugin install https://github.com/DietrichGebert/ponytail
```

它复用本仓库的 `gemini-extension.json`。区别在于，Antigravity 会把 `/ponytail` 命令转换成技能，因此你需要直接在聊天中输入它们（例如把 `/ponytail-review` 作为消息发送），而不是从斜杠菜单选择。在迁移完成前（预计 2026 年 6 月 18 日左右），`gemini extensions install` 仍然可用。若要将其作为常驻规则运行，请把规则集放入 `.agents/rules/`。

### Hermes Agent

```bash
hermes plugins install DietrichGebert/ponytail --enable
```

安装后重启 Hermes。插件会在每轮 LLM 调用前注入当前 Ponytail 模式，将随附技能注册为 `ponytail:<skill>`，并添加 `/ponytail`、`/ponytail-review`、`/ponytail-audit`、`/ponytail-debt`、`/ponytail-gain` 和 `/ponytail-help`。在共享网关中，请通过 Hermes 斜杠命令访问控制，将 `/ponytail` 限制为可信用户；运行时模式仅对当前进程生效。

### CodeWhale

CodeWhale 会读取项目根目录的 `AGENTS.md`，无需配置。把 [`AGENTS.md`](AGENTS.md) 复制到你的项目，或从本仓库检出中运行 `codewhale`。就这样。

### Swival

先把集合加入技能库，再添加需要的技能：

```bash
swival skills add --global https://github.com/DietrichGebert/ponytail  # 暂存到 ~/.config/swival/library
swival skills add ponytail                                             # 在当前项目安装集合
swival skills add --global ponytail                                    # 或在所有项目中启用
```

Swival 也会读取项目根目录的 `AGENTS.md` 和全局的 `~/.config/swival/AGENTS.md`，作为仅指令模式的后备方案。

在命令行中，用 `$` 前缀显式激活技能，例如 `$ponytail-review`。

### Devin CLI

```bash
devin plugins install DietrichGebert/ponytail
```

将 ponytail 安装为 Devin 插件；技能可通过 `/ponytail:ponytail`、`/ponytail:ponytail-review` 等命令使用。

### OpenClaw

```bash
clawhub install ponytail
```

从 ClawHub 将 ponytail 安装为 OpenClaw 技能；review、audit、debt、gain 和 help 技能也以相同方式安装（例如 `clawhub install ponytail-review`）。OpenClaw 会在编码任务中应用它，同时将其公开为 `/ponytail` 命令。不使用 ClawHub 时，可将 [`.openclaw/skills/ponytail`](.openclaw/skills/) 复制到 `~/.openclaw/skills/`。

### Grok Build

```bash
grok plugin install DietrichGebert/ponytail --trust
```

插件默认关闭。通过 `/plugins` → Plugins → 在 `ponytail` 上按空格启用，或在 `~/.grok/config.toml` 中配置：

```toml
[plugins]
enabled = ["ponytail"]
```

新建会话或重新加载插件。技能会显示为 `/ponytail`、`/ponytail-review`、`/ponytail-audit`、`/ponytail-debt`、`/ponytail-gain`、`/ponytail-help`。用 `grok inspect` 验证。Grok 可根据技能描述，在编码任务中自动调用 ponytail；需要显式激活时，使用 `/ponytail`（或 `/ponytail lite`、`/ponytail full`、`/ponytail ultra`）。Grok 不使用生命周期钩子，因为其 SessionStart 输出无法注入指令。

即使不安装插件，从检出运行时，`AGENTS.md` 仍可作为纯指令方案生效。

### Cursor

```bash
git clone https://github.com/DietrichGebert/ponytail
node ponytail/scripts/cursor-hooks.js install
```

这会把两个原生钩子合并进 `~/.cursor/hooks.json`（加 `--project` 则写入 `<project>/.cursor/hooks.json`），并保留原有钩子。条目会从该检出运行 `node`，所以请保持其路径不变；移动后需重新安装。Cursor 会在保存时重新加载文件；打开新聊天，默认级别的规则集会通过 `sessionStart` 注入。发送普通消息 `/ponytail lite`、`/ponytail full`、`/ponytail ultra` 或 `/ponytail off` 可在当前会话中切换级别；`/ponytail` 会报告当前级别。Cursor 的 `subagentStart` 无法注入上下文，所以子智能体不会使用规则集；云端智能体也不会触发 `sessionStart`。常驻规则（`.cursor/rules/ponytail.mdc`）与钩子二选一：工作区中存在该规则时，钩子不会注入内容，模式命令只会显示提示；删除规则即可让钩子管理级别。契约、验证记录和限制见 [docs/cursor-hooks.md](docs/cursor-hooks.md)。卸载命令：`node ponytail/scripts/cursor-hooks.js uninstall`。

就这些。他会感到骄傲。只是不会说出来。

ponytail 会在每个会话中激活，并提供少量命令（见[命令](#命令)）。当代码库与你有私人恩怨时，可以使用 `/ponytail ultra`。启动和切换模式时会显示当前模式。

使用环境变量 `PONYTAIL_DEFAULT_MODE`（`lite`/`full`/`ultra`/`off`），或在 `~/.config/ponytail/config.json`（Windows 为 `%APPDATA%\ponytail\config.json`）中设置 `defaultMode` 字段，可指定每个新会话的级别。默认值为 `full`。

激活后，规则集也会注入通过 Agent 工具启动的每个子智能体。若要仅针对特定智能体类型启用（例如排除只读搜索智能体），请设置 `PONYTAIL_SUBAGENT_MATCHER` 环境变量；它是一个针对子智能体 `agent_type` 进行匹配的正则表达式，不锚定且不区分大小写：`explore|general` 匹配两者，`^general$` 为精确匹配，插件智能体类型类似 `plugin:name`。未设置时默认注入所有子智能体；正则无效或平台不提供智能体类型时，也会回退到全部注入。

Cursor（仅规则模式，是[钩子安装](#cursor)的替代方案）、Windsurf、Cline、GitHub Copilot Chat（VS Code、JetBrains 和 Visual Studio 编辑器扩展，不是[安装](#安装)一节中的独立 Copilot CLI）、Aider、Kiro、Zed、CodeWhale、Swival、Qoder：从本仓库复制对应的规则文件（[`.cursor/rules/`](.cursor/rules/)、[`.windsurf/rules/`](.windsurf/rules/)、[`.clinerules/`](.clinerules/)、[`.github/copilot-instructions.md`](.github/copilot-instructions.md)、[`AGENTS.md`](AGENTS.md)、[`.kiro/steering/`](.kiro/steering/)、[`.qoder/rules/`](.qoder/rules/)）。

Kiro：将 `.kiro/steering/ponytail.md` 复制到 `~/.kiro/steering/`（全局）或项目的 `.kiro/steering/`。

GitHub Copilot CLI 后备方案（仅指令模式）：它会读取项目中的 `AGENTS.md` 和 `.github/copilot-instructions.md`；也可把规则复制到 `~/.copilot/copilot-instructions.md`，让 ponytail 在所有项目中生效。此方式保留常驻指导，但不提供插件的模式切换和钩子。

VS Code 的 Codex 扩展会读取本仓库自带的 `AGENTS.md`，因此从仓库根目录运行无需配置（将文件放在 `~/.codex/AGENTS.md` 可让 Codex 全局使用）。

JetBrains Junie 可以读取 `AGENTS.md`，但目前不会自动发现。请在 Settings → Tools → Junie → Project Settings → Guidelines Path 中指向该文件。本仓库自带 `AGENTS.md`；`.junie/guidelines.md` 是 Junie 的旧路径。

Amp（Sourcegraph）会从工作目录及其父目录一直读取 `AGENTS.md` 到 `$HOME`，因此本仓库无需配置即可使用（`~/.config/amp/AGENTS.md` 可用于全局配置）。

Jules（Google）会读取仓库根目录的 `AGENTS.md`，因此无需配置即可加载规则集。

各智能体对应哪些文件，参见[智能体可移植性](docs/agent-portability.md)。

### 卸载

| 宿主 | 命令 |
|------|------|
| Claude Code | `/plugin remove ponytail` |
| Codex | `codex plugin remove ponytail` |
| Devin CLI | `devin plugins remove ponytail` |
| Grok Build | `grok plugin uninstall ponytail` |
| Pi agent | `pi uninstall ponytail` |
| Cursor hooks | `node scripts/cursor-hooks.js uninstall`（项目级安装加 `--project`）；仅删除 `hooks.json` 中 ponytail 的条目 |
| Cursor 规则 / Windsurf / Cline / Qoder 等 | 删除复制过去的规则文件 |

以上命令会删除插件自身文件，但会保留 ponytail 写入插件目录之外的少量状态：模式标志（`~/.claude/.ponytail-active`，Cursor 则为 `~/.cursor/.ponytail-active`）、`~/.config/ponytail/config.json`、`~/.cursor/hooks.json` 中 ponytail 的条目，以及（如果接受了设置提示）`~/.claude/settings.json` 中的 `statusLine` 条目。运行 `node scripts/uninstall.js` 可一并清理。**请在上面的宿主卸载命令之前运行它**——脚本本身属于插件文件，先删除插件就无法再运行（也可以从本仓库的另一份检出运行）。脚本仅会在 `statusLine` 指向 ponytail 自带脚本时删除该条目，不会影响你自行配置的状态栏。

## 命令

| 命令 | 作用 |
|------|------|
| `/ponytail [lite \| full \| ultra \| off]` | 设置强度或关闭 ponytail。无参数时，若当前关闭则按默认级别开启，否则报告当前级别。 |
| `/ponytail-review` | 检查当前 diff 中的过度设计，并返回一份可删除项清单。 |
| `/ponytail-audit` | 审计整个仓库中的过度设计，而不只是当前 diff。 |
| `/ponytail-debt` | 把延期处理的 `ponytail:` 捷径收集到台账中，免得“以后”变成“永不”。 |
| `/ponytail-gain` | 显示基准测试测得的收益榜（更少代码、更低成本、更快速度）。 |
| `/ponytail-help` | 以上命令的快速参考。 |

这些命令需要支持技能的宿主（Claude Code、Codex、Devin CLI、OpenCode、Gemini、pi、Swival、Hermes Agent、Qoder、Grok Build）。在 Codex CLI 和 IDE 扩展中，它们属于技能，请用 `$ponytail-review` 调用。使用[钩子](#cursor)的 Cursor 仅支持 `/ponytail` 级别切换，需要作为普通消息输入。纯指令适配器（Cursor 规则文件、Windsurf、Cline、Copilot、Kiro、Antigravity）只加载常驻规则集，不提供这些命令。

## 开发

修改精简版规则文本时，请保持各智能体副本一致：

```bash
node scripts/check-rule-copies.js
npm test
```

OpenClaw 技能包（`.openclaw/skills/`）由 `skills/` 生成；修改技能后请重新运行 `node scripts/build-openclaw-skills.js`，否则测试套件会因内容过期而失败。发布技能到 ClawHub 时，先运行一次 `clawhub login`，再运行 `node scripts/publish-openclaw-skills.js`（它会按 `package.json` 中的版本发布全部六项技能；传入 `--dry-run` 可预览）。

正确性基准测试会调用 Python 验证电子邮件和 CSV；它会先尝试 `python3`，再尝试 `python`。CSV 检查需要在本地安装 `pandas`。

## 常见问题

**可以和 [caveman](https://github.com/JuliusBrussee/caveman) 一起用吗？**  
可以，而且应该这么做。Caveman 精简智能体说的话，ponytail 精简智能体造的东西。两者各管一半，互不重叠：caveman 保证代码逐字节不变，ponytail 不碰表达方式。用最短的话，聊最小的代码。

**需要配置文件吗？**  
不需要。可选的 `~/.config/ponytail/config.json` 或 `PONYTAIL_DEFAULT_MODE` 环境变量可以设置默认级别，但都不是必需的。

**如果我真的需要那个 120 行的缓存类呢？**  
你不需要。非要坚持的话，他还是会写。慢慢地。正确地。看着你写。

**它能扩展吗？**  
你从未写下的代码可以无限扩展。零 bug，零 CVE，自古以来 100% 在线。

**为什么叫“ponytail”？**  
你明明知道为什么。

## 赞助商

<p align="center">
  <a href="https://greenpt.com/">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="assets/logo-greenpt-dark.svg">
      <img src="assets/logo-greenpt.svg" width="260" alt="GreenPT">
    </picture>
  </a>
</p>

## 许可证

[MIT](LICENSE)。能用的最短许可证。

## Star 历史

<a href="https://www.star-history.com/dietrichgebert/ponytail#history">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=DietrichGebert/ponytail&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=DietrichGebert/ponytail&type=Date" />
   <img alt="Star 历史图" src="https://api.star-history.com/chart?repos=DietrichGebert/ponytail&type=Date" />
 </picture>
</a>
