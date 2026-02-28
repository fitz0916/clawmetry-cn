# 🦞 ClawMetry 中文版

[![PyPI](https://img.shields.io/pypi/v/clawmetry)](https://pypi.org/project/clawmetry/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/vivekchand/clawmetry)](https://github.com/vivekchand/clawmetry/stargazers)

**看透你的 AI 代理思维。** [OpenClaw](https://github.com/openclaw/openclaw) AI 代理的实时监控面板。

一行命令，无需配置，自动检测一切。

```bash
pip install clawmetry && clawmetry
```

启动后访问 **http://localhost:8900** 即可。

## 功能特性

- **流程 (Flow)** — 实时动画展示消息通过通道、大脑、工具的流转
- **概览 (Overview)** — 健康检查、活动热图、会话数量、模型信息
- **使用量 (Usage)** — Token 和费用统计，日/周/月明细
- **会话 (Sessions)** — 活跃代理会话，包含模型、Token、最后活动
- **定时任务 (Crons)** — 定时任务状态、下次运行时间、持续时间
- **日志 (Logs)** — 实时彩色日志流
- **记忆 (Memory)** — 浏览 SOUL.md、MEMORY.md、AGENTS.md 和每日笔记
- **对话记录 (Transcripts)** — 气泡界面的会话历史

## 安装

**pip (推荐):**
```bash
pip install clawmetry
clawmetry
```

**一键安装:**
```bash
curl -sSL https://raw.githubusercontent.com/vivekchand/clawmetry/main/install.sh | bash
```

**源码安装:**
```bash
git clone https://github.com/vivekchand/clawmetry.git
cd clawmetry && pip install flask && python3 dashboard.py
```

## 配置

大多数用户不需要任何配置。ClawMetry 会自动检测你的工作区、日志、会话和定时任务。

如需自定义：

```bash
clawmetry --port 9000              # 自定义端口 (默认: 8900)
clawmetry --host 127.0.0.1         # 仅绑定本地
clawmetry --workspace ~/mybot      # 自定义工作区路径
clawmetry --name "Alice"           # 你的名字（流程图显示用）
```

查看所有选项：`clawmetry --help`

## 支持的通道

ClawMetry 可显示所有已配置 OpenClaw 通道的实时活动。只有在 `openclaw.json` 中配置的通道才会显示在流程图中。

| 通道 | 状态 | 实时弹窗 | 备注 |
|------|------|----------|------|
| 📱 **Telegram** | ✅ 完整 | ✅ | 消息、统计、10秒刷新 |
| 💬 **iMessage** | ✅ 完整 | ✅ | 直接读取 `~/Library/Messages/chat.db` |
| 💚 **WhatsApp** | ✅ 完整 | ✅ | 通过 WhatsApp Web (Baileys) |
| 🔵 **Signal** | ✅ 完整 | ✅ | 通过 signal-cli |
| 🟣 **Discord** | ✅ 完整 | ✅ | 服务器 + 频道检测 |
| 🟪 **Slack** | ✅ 完整 | ✅ | 工作区 + 频道检测 |
| 🌐 **Webchat** | ✅ 完整 | ✅ | 内置 Web UI 会话 |
| 📡 **IRC** | ✅ 完整 | ✅ | 终端风格气泡界面 |
| 🍏 **BlueBubbles** | ✅ 完整 | ✅ | 通过 BlueBubbles REST API 的 iMessage |
| 🔵 **Google Chat** | ✅ 完整 | ✅ | 通过 Chat API webhooks |
| 🟣 **MS Teams** | ✅ 完整 | ✅ | 通过 Teams bot 插件 |
| 🔷 **Mattermost** | ✅ 完整 | ✅ | 自托管团队聊天 |
| 🟩 **Matrix** | ✅ 完整 | ✅ | 去中心化、E2EE 支持 |
| 🟢 **LINE** | ✅ 完整 | ✅ | LINE Messaging API |
| ⚡ **Nostr** | ✅ 完整 | ✅ | 去中心化 NIP-04 DMs |
| 🟣 **Twitch** | ✅ 完整 | ✅ | 通过 IRC 连接 |
| 🔷 **飞书/Lark** | ✅ 完整 | ✅ | WebSocket 事件订阅 |
| 🔵 **Zalo** | ✅ 完整 | ✅ | Zalo Bot API |

> **自动检测：** ClawMetry 会读取你的 `~/.openclaw/openclaw.json` 并只渲染你实际配置的通道。无需手动设置。

## 环境要求

- Python 3.8+
- Flask (通过 pip 自动安装)
- OpenClaw 运行在同一台机器上
- Linux 或 macOS

## 云端部署

参考 **[云端测试指南](docs/CLOUD_TESTING.md)** 了解 SSH 隧道、反向代理和 Docker 部署。

## 测试

本项目使用 BrowserStack 进行测试。

[![BrowserStack](https://automate.browserstack.com/badge.svg)](https://browserstack.com)

## 许可证

MIT

---

<p align="center">
  <strong>🦞 看透你的 AI 代理思维</strong><br>
  <sub>由 <a href="https://github.com/vivekchand">@vivekchand</a> 构建 · <a href="https://clawmetry.com">clawmetry.com</a> · <a href="https://github.com/openclaw/openclaw">OpenClaw</a> 生态的一部分</sub>
</p>
