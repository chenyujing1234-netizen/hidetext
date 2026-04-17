---
name: HideText 隐藏图生成
description: 将文字（微信号、手机号、联系方式等）隐藏到 AI 生成的艺术图片中。人眼可识别，但 AI/OCR 难以检测，适用于小红书、抖音、闲鱼等平台引流。免费使用，每天 30 次。
version: 1.0.0
author: HideText
homepage: https://www.hidetext.cloud
tags:
  - image
  - hide-text
  - social-media
  - anti-detection
  - 图片生成
  - 隐藏文字
---

# HideText 隐藏图生成

## 功能说明

将用户提供的文字（联系方式、微信号、手机号等）隐藏到 AI 生成的艺术图片中：

- 人眼可以清晰识别文字内容
- AI 审核系统和 OCR 工具难以自动检测
- 适合在小红书、抖音、闲鱼等平台中传递联系方式

## 使用场景

当用户需要在社交平台发布包含联系方式的图片，但又担心被平台 AI 检测屏蔽时，调用本技能生成隐藏图。

## 调用方式

向 `https://www.hidetext.cloud/api/skill/generate` 发送 POST 请求：

```json
{
  "text": "微信: abc123456",
  "mode": "text-confusion"
}
```

## 参数说明

| 参数 | 类型 | 必填 | 说明 |
|------|------|------|------|
| text | string | 是 | 要隐藏的文字，如"微信: abc123456" |
| mode | string | 否 | 隐藏风格，默认 text-confusion |

## 支持的风格（mode）

| 风格值 | 说明 | 推荐场景 |
|--------|------|----------|
| text-confusion | 文字物品混淆（默认推荐） | 通用，效果最佳 |
| water-ripple | 水波纹扭曲 | 文艺清新风 |
| life-scene | 生活场景融入 | 最自然不易察觉 |
| interference-lines | 干扰线混淆 | 视觉冲击强 |
| geometric | 几何艺术 | 简洁现代风 |
| multi-layer | 多层叠加 | 复杂隐藏效果 |
| text-trypophobia | 活字印刷密集风 | 文字艺术风格 |
| poker-card | 扑克牌风格 | 最快（本地生成） |

## 完整示例

**请求：**

```http
POST https://www.hidetext.cloud/api/skill/generate
Content-Type: application/json

{
  "text": "微信: abc123456",
  "mode": "water-ripple"
}
```

**成功响应：**

```json
{
  "success": true,
  "imageUrl": "https://www.hidetext.cloud/images/2026-04-17T10-00-00_user0_water-ripple.png",
  "mode": "water-ripple"
}
```

**错误响应：**

```json
{
  "success": false,
  "message": "请提供 text 参数（要隐藏的文字内容）"
}
```

## 使用限制

- 免费使用，每个 IP 地址每天最多 30 次
- 生成的图片链接有效期 24 小时
- 支持中文、英文、数字、符号等各类文字

## 相关链接

- 在线体验：https://www.hidetext.cloud
- OpenAPI 规范：https://www.hidetext.cloud/openapi.yaml
- MCP 接入（SSE）：https://www.hidetext.cloud/mcp/sse
