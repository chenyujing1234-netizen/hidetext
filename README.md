# HideText 隐藏图生成

> 将文字（微信号、手机号、联系方式等）隐藏到 AI 生成的艺术图片中。人眼可识别，但 AI/OCR 难以检测。

[![在线体验](https://img.shields.io/badge/在线体验-hidetext.cloud-blue)](https://www.hidetext.cloud)
[![免费 API](https://img.shields.io/badge/免费API-每天30次-green)](https://www.hidetext.cloud/api/skill/generate)

## 功能特点

- 人眼可清晰识别文字内容
- AI 审核系统和 OCR 工具难以自动检测
- 支持 8 种隐藏风格
- **完全免费**，每 IP 每天 30 次

## 支持的隐藏风格

| 风格 | 说明 |
|------|------|
| text-confusion | 文字物品混淆（默认推荐）|
| water-ripple | 水波纹扭曲 |
| life-scene | 生活场景融入 |
| interference-lines | 干扰线混淆 |
| geometric | 几何艺术 |
| multi-layer | 多层叠加 |
| text-trypophobia | 活字印刷密集风 |
| poker-card | 扑克牌风格（最快）|

## 快速调用

```bash
curl -X POST https://www.hidetext.cloud/api/skill/generate \
  -H "Content-Type: application/json" \
  -d '{"text": "微信: abc123456", "mode": "water-ripple"}'
```

响应：

```json
{
  "success": true,
  "imageUrl": "https://www.hidetext.cloud/images/xxx.png",
  "mode": "water-ripple"
}
```

## AI 平台接入

| 平台 | 接入方式 |
|------|----------|
| LobeChat 插件 | [manifest.json](https://www.hidetext.cloud/lobe-plugin/manifest.json) |
| Cursor / Claude (MCP) | `https://www.hidetext.cloud/mcp/sse` |
| Coze / 文心 / 通义 | [openapi.yaml](https://www.hidetext.cloud/openapi.yaml) |
| Agent Skill Hub | 本仓库 `SKILL.md` |

## 相关链接

- 在线体验：https://www.hidetext.cloud
- OpenAPI 规范：https://www.hidetext.cloud/openapi.yaml
- MCP SSE：https://www.hidetext.cloud/mcp/sse
