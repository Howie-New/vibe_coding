### 1. 项目初始化与上下文管理 (Initialization & Context)

- **`/init`**: 通读当前文件夹下的所有文件进行分析，并将项目知识保存到 `CLAUDE.md` 文件中，作为后续对话的上下文。
- **`/compact`**: 压缩对话上下文，排除不重要的内容，以提高 AI 专注度并显著降低 Token 消耗。
- **`/clear`**: 清除当前的对话历史记录，在开启新任务时保持干净的上下文。

### 2. 交互增强命令 (Advanced Interaction)

- **`! [command]`**: 切换到命令行模式执行临时命令（如 `npm install`）。执行过程和结果会自动加入对话上下文，防止 AI 重复操作。
- **`# [memory]`**: 进入记忆模式。输入的内容会被记录为长期记忆，可选择保存至项目级 (`CLAUDE.md`) 或用户全局配置文件中。
- **`/ide [vscode]`**: 将 Claude Code 与 IDE（如 VS Code）打通。支持感知 IDE 中选中的代码，并在 IDE 中直观展示代码修改差异。
- **`claude -p "prompt"`**: 非交互模式。作为命令行助手开启一次性对话，处理完任务后直接打印结果并退出。 [[04:50](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=290)]

### 3. 模型推理控制 (Reasoning Control)

- **`sync`, `hard`, `ultra`**: 在提问前加上这些前缀，用于控制模型思考的长度和强度（强度逐级递增），适用于复杂的推理任务。 [[02:13](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=133)]

### 4. MCP 协议支持 (Model Context Protocol)

- **`claude mcp add <name> -- npx <command>`**: 安装 MCP Server，扩展 AI 的外部工具能力（如连接数据库、搜索最新文档等）。 [[05:31](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=331)]
- **`claude mcp remove <name>`**: 移除已安装的 MCP Server。 [[07:13](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=433)]
- **`/mcp`**: 在交互界面中查看当前已安装的 MCP 服务列表。 [[06:13](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=373)]

### 5. 自动化与权限管理 (Automation & Permissions)

- **`permissions`**: 自定义工具调用规则。可以将特定工具（如 `bash`）加入 `allow` 列表，实现自动执行而无需人工确认。 [[08:23](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=503)]
- **`--dangerously-skip-permissions`**: 在启动 Claude Code 时添加此参数，将赋予 AI 最高权限，跳过所有工具执行的申请步骤。 [[09:31](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=571)]

### 6. 自定义扩展 (Customization)

- **Custom Commands**: 在 `.claude/commands/` 下创建 `.md` 文件即可定义新命令，支持使用 `$argument` 传递参数。 [[09:56](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=596)]
- **Hooks**: 在 `settings.json` 中配置 `hooks`（如 `post-tool-use`），在特定节点（如修改文件后）自动执行特定操作（如格式检查）。 [[12:30](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=750)]
- **`/subagent create`**: 创建子智能体（Subagent）。将复杂任务拆解并并行处理，提高执行效率和结果的可预测性。 [[13:09](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=789)]

### 7. 工作流与历史管理 (Workflow & History)

- **`/resume`**: 找回并恢复之前的历史对话主题。 [[16:43](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=1003)]
- **`/export`**: 将当前的对话内容复制到剪贴板，方便保存或提供给其他 AI 进行交叉验证。 [[17:28](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=1048)]
- **GitHub Integration**: 配合 GitHub CLI (`gh`)，可让 Claude Code 自动读取 Issue、修复 Bug 并推送代码回仓库。 [[15:29](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=929)]

视频中提到的 **Claudia** 是一个基于 Claude Code 的桌面可视化应用，它额外提供了 **Time Navigation (Checkpoint)** 功能，支持同时回退对话历史和文件改动状态。 [[20:52](http://www.youtube.com/watch?v=e5O8A5pcVgg&t=1252)]