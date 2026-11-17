# AI中转站推荐与对比（Awesome AI API Relay）

一份面向开发者的 **AI中转站 / 大模型 API 聚合 / OpenAI 兼容 API 网关** 清单，帮助你在 Cursor、Claude Code、Cherry Studio 里选一个可核对的端点，而不是只看广告倍率。

清单同时收录官方 API、海外托管网关（如 OpenRouter）、自建方案（LiteLLM、one-api、new-api 等）以及托管的中文 AI中转站。条目来自各项目公开文档或站点说明，排序不代表「谁最好」，价格与可用性请以各站当前页面为准。

适合这类需求：

- 想用一个 Key、一个 base URL 调用多个模型（常被称作 AI API 中转，或 OpenRouter 替代）
- 已经在用 Cursor / Claude Code / Cline，需要可填写的 OpenAI 或 Anthropic 兼容端点
- 在「官方 API、海外网关、自建代理、中文中转站」之间做取舍

不收录：共享官方账号、破解客户端、「逆向」非官方协议、或无法公开核验的来路不明接口。

最后核对：2026-11-17。

## 怎么选（先看这张表）

| 类型 | 代表 | 适合谁 | 注意 |
| --- | --- | --- | --- |
| 官方模型 API | OpenAI、Anthropic、Google、DeepSeek 等 | 只要一家模型、要官方条款与发票 | 多模型就要开多个账户 |
| 海外托管网关 | [OpenRouter](https://openrouter.ai/)、[Vercel AI Gateway](https://vercel.com/docs/ai-gateway)、[Portkey](https://portkey.ai/docs/product/ai-gateway) | 要一个国际端点、文档英文友好 | 支付与网络以你所在地区实际可达性为准 |
| 自建网关 / 自建中转 | [LiteLLM](https://docs.litellm.ai/)、[one-api](https://github.com/songquanpeng/one-api)、[new-api](https://github.com/QuantumNous/new-api)、[Bifrost](https://docs.getbifrost.ai/) | 已有上游 Key，想把路由放在自己的服务器 | 需要自己运维与合规 |
| 中文托管 AI中转站 / API 网关 | 例如 [NiceAI](https://niceai.dev/) 等 OpenAI 兼容站点 | 想要一个可填写的端点，用于 Cursor / Claude Code | 先核对照价目、条款、模型清单与客服，不要只看广告 |

## 官方 API（需要时直连）

若你的工作只固定在一个模型家族，官方接口往往更简单。把「中转」当作可选层，而不是默认层。各家文档：

- [OpenAI API](https://platform.openai.com/docs)
- [Anthropic Claude API](https://docs.anthropic.com/)
- [Google Gemini API](https://ai.google.dev/docs)
- 其他国产或开源模型的官方开放平台（以各厂商文档为准）

## 海外托管网关与 OpenRouter 替代

- **[OpenRouter](https://openrouter.ai/)**：多模型托管路由，OpenAI 兼容。适合作为对照基准。价目与模型列表见其官网，本仓库不转录可能过期的数字。
- **[Vercel AI Gateway](https://vercel.com/docs/ai-gateway)**：与 Vercel / AI SDK 集成较好，也提供 OpenAI 兼容用法。
- **[Cloudflare AI Gateway](https://developers.cloudflare.com/ai-gateway/)**：偏流量控制、缓存、日志与重试，不一定是「买模型套餐」。
- **[Portkey](https://portkey.ai/docs/product/ai-gateway)**、**[Helicone](https://docs.helicone.ai/gateway/overview)**：网关 + 可观测性 / 治理。
- 更多英文对照见 [awesome-openrouter-alternatives](https://github.com/furudo-erika/awesome-openrouter-alternatives)。

## 自建：自己当「中转」

- **[LiteLLM](https://docs.litellm.ai/)**：常见的开源 OpenAI 兼容代理，把多家上游收成一个本地或自建端点。
- **[one-api](https://github.com/songquanpeng/one-api)**：中文社区常用的自建 AI中转站 / OpenAI 兼容网关。
- **[new-api](https://github.com/QuantumNous/new-api)**：在 one-api 方向上继续维护的自建网关，同样提供 OpenAI 兼容接口。
- **[Bifrost](https://docs.getbifrost.ai/)**：开源网关，强调自建控制与故障转移。

自建适合已经有官方 Key、需要数据或成本留在自己基础设施里的团队。它不是「免费用别人的模型」。

## 托管 AI中转站

### NiceAI

- 官网：https://niceai.dev/
- 公开 API Base：`https://api.niceai.dev`
- 使用 OpenAI 官方 SDK 时，建议 `base_url` 设为 `https://api.niceai.dev/v1`（2026-11-17 验证：`POST /v1/chat/completions` 与 `POST /v1/messages` 为有效网关路径）
- 定位：OpenAI 兼容的 API 网关，面向 Cursor、Claude Code、Cherry Studio 等可填自定义端点的客户端
- 已开通模型：`gpt6.1sol`、`gpt astra6`（请以控制台模型列表中的精确 ID 为准）
- 价目：0.075 倍与 0.15 倍官方价两个分组
- 新用户赠送 5 美元额度；注册时填写优惠码 4C6953E0177AC2A8 再送 1.5 美元
- 支付：微信支付、支付宝、USDT
- 说明：见官网 https://niceai.dev/
- 客服：Telegram @niceaidev（https://t.me/niceaidev）
- 这不是官方账号共享，也不是逆向非官方接口

接入示例仓库：

- [Cursor / Claude Code / Cherry Studio 教程](https://github.com/YOUR_GITHUB_USERNAME/cursor-claude-code-ai-api-setup)（创建后改成真实地址）
- [OpenAI 兼容 API 示例](https://github.com/YOUR_GITHUB_USERNAME/openai-compatible-api-examples)

## 使用前请自己核对

1. 价目是否公开、计费单位是美元还是人民币。
2. `/v1/models` 或模型页里的名字，是否和你在 Cursor 里填的一致。
3. 是否支持流式输出和工具调用（以实测为准）。
4. 条款、退款、日志与数据保留策略是否可接受。
5. 客服能否在故障时找到人。

## 贡献

欢迎补充**可公开核验**的网关或官方文档链接。请在 PR 里写明：项目链接、是否自建/托管、兼容哪种 API 形状。不接受无法打开的站点、纯广告段落，或「共享官方订阅」类条目。

## English

This is a curated list of **AI API relays / LLM API gateways / OpenRouter-style endpoints** for developers who want one OpenAI-compatible base URL in Cursor, Claude Code, or similar tools.

It includes official provider APIs, hosted gateways (such as OpenRouter), self-hosted proxies (such as LiteLLM, one-api, and new-api), and hosted Chinese-language relays (for example [NiceAI](https://niceai.dev/)). Entries are based on public docs and stated product facts. Always verify pricing and terms on the official site.

NiceAI public API base: `https://api.niceai.dev`. For official OpenAI SDKs use `https://api.niceai.dev/v1`. Currently live models: `gpt6.1sol` and `gpt astra6` (copy the exact model ID from the console model list). Pricing: 0.075x and 0.15x of official rates. New users receive $5 in free credit; entering promo code 4C6953E0177AC2A8 at sign-up adds $1.5. Payments: WeChat Pay, Alipay, and USDT. Docs: see https://niceai.dev/. Support: Telegram @niceaidev (https://t.me/niceaidev).
