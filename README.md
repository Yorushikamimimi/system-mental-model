# System Mental Model · 系统心智模型

一个帮助你理解系统如何运转、并检验自己是否理解的 Agent Skill。先用业务链路连接组件与机制，再用失败场景、变式或方案取舍检查判断；需要亲自掌握操作时，保留本人首版与修改过程。

**AI 做出了成果、你能复述答案、你能独立判断、你能独立实现，是不同的证据。** 这个 Skill 会把它们分开，不把运行成功直接当成你学会了。

## 适合什么任务

- 学一个项目：从一次请求到最终结果，理解数据流、状态与模块职责。
- 学一个机制：把事务、重试、缓存等连接到它解决的具体问题。
- 学排障：判断哪些证据能区分可能原因。
- 比较方案：解释收益、成本与适用边界，检查 AI 的建议。

普通查定义、让 AI 代办或日常代码修改，不强制套教学流程。只想听讲解时无需编码、测验或画图。它不提供完整课程、不自动安排作业，也不保证使用后一定掌握。

## 安装到 Codex

仓库中的可安装目录是 `skills/system-mental-model/`。该 Skill 只有 Markdown 与界面元数据，不需要额外软件、MCP 或网络服务。

下载本仓库到你选择的位置，然后把此目录复制到 Codex 支持的 Skills 目录。下面以统一目录 `~/.agents/skills` 为例；已有同名目录时停止，先检查内容，避免覆盖：

```bash
git clone https://github.com/Yorushikamimimi/system-mental-model.git
mkdir -p "$HOME/.agents/skills"
if [ -e "$HOME/.agents/skills/system-mental-model" ] || [ -L "$HOME/.agents/skills/system-mental-model" ]; then
  echo "同名 Skill 已存在，请先检查；本次不覆盖。"
else
  cp -R system-mental-model/skills/system-mental-model "$HOME/.agents/skills/system-mental-model"
fi
```

也可使用当前实例自己的 `$CODEX_HOME/skills`；未设置 `CODEX_HOME` 时为 `~/.codex/skills`。只选择一个发现路径，避免重复安装；自定义环境应先确认其归属。打开新的 Codex 会话，确认能发现 `system-mental-model`。具体刷新行为以客户端版本为准。

其他支持 `SKILL.md` 的 Agent 可按其文档导入目录；尚未逐个客户端验证兼容性。卸载时仅移除自己安装的同名目录，不修改其他 Skills。

## 如何调用

```text
使用 $system-mental-model，帮我理解这个预约服务。
我有 20 分钟，知道基本 SQL，但没弄懂事务和并发控制的区别。
从一条预约链路讲起，依据我提供的代码说明；先讲解，再问一个变式问题。
```

```text
使用 $system-mental-model，帮我判断“请求超时就立即重试”这个建议。
目前只有客户端错误信息。请区分已知和未知，并说明下一步需要什么证据。
```

正常自动发现可用；并非每轮都会或都应该触发。实际触发取决于 Agent 对请求的判断，显式调用更清楚。

## 工作方式

确认最小目标与证据 → 解释一条链路 → 连接关键机制 → 按意愿与时间检查理解 → 简短留停点。环节可按基础跳过，不要求固定题量。

[Skill 主体](skills/system-mental-model/SKILL.md)包含证据边界、渐进教学和停止条件。[原创示例](skills/system-mental-model/references/examples.md)展示预约、报表重试及缓存取舍，也提供行为走查情境。

## 版本与验证

当前版本：**0.1.0**。交付状态与验证边界见 [CURRENT_PROGRESS.md](CURRENT_PROGRESS.md)。格式检查通过不等于教学效果经过实验；最终掌握仍需用户的真实首答、迁移判断与实际操作证据。

## 许可证与来源边界

本仓库的教学指令、说明与虚构示例为本项目原创表达，以 [MIT License](LICENSE) 发布。没有附带第三方文章、视频、私有笔记或他人的学习 Prompt，也不声称第三方作者背书。引用或加入外部材料时，应分别核对来源及授权；本仓库许可证不会授予那些材料的权利。
