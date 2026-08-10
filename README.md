# MWS Auto Renew ☁️

MWS（cloud.puratya.com）Bot 自动续期脚本 + GitHub Actions 工作流。

## 功能

- 🤖 每天定时续期 MWS Bot（北京时间 18:00）
- 🔄 支持手动触发
- 📊 获取 Bot 状态、剩余时间
- 📱 Telegram 通知（可选）
- 🧹 自动清理旧的运行记录

## 快速开始

### 1. 配置 Secrets

在仓库 **Settings → Secrets and variables → Actions** 添加：

| Secret | 说明 | 必填 |
|--------|------|------|
| `SESSION_TOKEN` | MWS Bearer Token | ✅ |
| `GH_TOKEN` | GitHub PAT（用于清理记录） | ✅ |
| `TG_BOT_TOKEN` | Telegram Bot Token | ❌ |
| `TG_CHAT_ID` | Telegram Chat ID | ❌ |
| `DISCORD_TOKEN` | Discord Token（用于重新授权） | ❌ |

### 2. 获取 SESSION_TOKEN

```bash
# 直接调用 API
curl -H "Authorization: Bearer <你的JWT>" https://cloud-api.puratya.com/auth/me
```

### 3. 修改 Bot ID

编辑 `mws_renew.py` 中的 `BOT_IDS` 列表：

```python
BOT_IDS = [9329]  # 替换为你的 Bot ID
```

## 定时时间

| 时区 | 时间 |
|------|------|
| UTC | 10:00 |
| 北京时间 | 18:00 |

## 技术栈

- Python 3.12
- GitHub Actions
- MWS REST API

## 许可证

MIT