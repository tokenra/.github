# TokenRa

**One API key for DeepSeek, GLM, Kimi, Qwen, MiniMax, GPT Image, Seedance and Jev.**

TokenRa is an independent, OpenAI-compatible AI API gateway. Point any OpenAI SDK at `https://tokenra.io/v1` and switch models by changing one string. You pay per use, with no subscription.

[Website](https://tokenra.io) · [Get an API key](https://tokenra.io/register) · [Models & pricing](https://tokenra.io/models.html) · [Docs](https://tokenra.io/docs.html) · [Examples](https://github.com/tokenra/tokenra-api-examples) · [中文](#中文)

> **Latest:** 🆓 [MiniMax M3.1 Flash](https://tokenra.io/models/minimax-m3.1-flash-api.html) is free on TokenRa until October 31, 2026 · 🧠 [DeepSeek V4.1 Flash 1017](https://tokenra.io/models/deepseek-v4.1-flash-1017.html) is live · 🎯 [Jev](https://tokenra.io/models/jev-api.html) returns typed decisions instead of text

---

## Quickstart

```bash
curl https://tokenra.io/v1/chat/completions \
  -H "Authorization: Bearer $TOKENRA_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "deepseek-v4.1-flash",
    "messages": [{"role": "user", "content": "Hello!"}]
  }'
```

With the OpenAI Python SDK, only the key and the base URL change:

```python
from openai import OpenAI

client = OpenAI(api_key="YOUR_TOKENRA_KEY", base_url="https://tokenra.io/v1")
reply = client.chat.completions.create(
    model="deepseek-v4.1-flash",
    messages=[{"role": "user", "content": "Hello!"}],
)
print(reply.choices[0].message.content)
```

## Start here

| What you need | Link | Use it for |
| --- | --- | --- |
| API key | [Register](https://tokenra.io/register) | One key for every enabled model |
| Code examples | [tokenra-api-examples](https://github.com/tokenra/tokenra-api-examples) | cURL, Python, Node.js and Go: chat, streaming, tool calling, vision, images, video, Jev |
| Model catalog | [models.html](https://tokenra.io/models.html) | Model IDs, developers and live rates |
| API docs | [docs.html](https://tokenra.io/docs.html) | Authentication, endpoints and request formats |
| Framework setup | [integrations](https://github.com/tokenra/tokenra-api-examples/tree/main/integrations) | LangChain, Vercel AI SDK, Claude Code, OpenCode |
| Data handling | [Zero Data Retention](https://tokenra.io/zero-data-retention.html) | How TokenRa handles request content |

## Endpoints

| Endpoint | What it does |
| --- | --- |
| `POST /v1/chat/completions` | OpenAI-compatible chat, streaming, tools and image input |
| `POST /v1/images/generations` | Image generation (GPT Image 2.5) |
| `POST /v1/video/generations` | Asynchronous video tasks (Seedance); poll `GET /v1/video/generations/{task_id}` |
| `POST /v1/decisions` | Typed decisions with Jev |
| `GET /v1/models` | The models your key can call |

## Models

| Model | Model ID | Developer |
| --- | --- | --- |
| [DeepSeek V4.1 Flash](https://tokenra.io/models/deepseek-v4.1-flash-api.html) | `deepseek-v4.1-flash` | DeepSeek |
| [GLM-5.3-Flash](https://tokenra.io/models/glm-5-3-flash.html) | `glm-5.3-flash` | Z.ai |
| [Kimi K3](https://tokenra.io/models/kimi-k3-api.html) | `kimi-k3` | Moonshot AI |
| [Qwen3.8-Omni-Flash](https://tokenra.io/models/qwen-3.8-omni-flash.html) | `qwen3.8-omni-flash` | Alibaba Qwen |
| [MiniMax M3.1 Flash](https://tokenra.io/models/minimax-m3.1-flash-api.html) | `minimax-m3.1-flash` | MiniMax |
| [GPT Image 2.5](https://tokenra.io/models/gpt-image-2-5.html) | `gpt-image-2.5-flare` | OpenAI |
| [Seedance 2.0](https://tokenra.io/models/seedance-2-0-api.html) / [2.5](https://tokenra.io/models/seedance-2-5-api.html) | `seedance-2-0-pro`, `artsdance-2-5-pro-260801` | ByteDance |
| [Jev](https://tokenra.io/models/jev-api.html) | `jev-latest` | TypeSafe |

More models and live rates are in the [model catalog](https://tokenra.io/models.html). TokenRa is an independent gateway; model names belong to their developers.

---

## 中文

**一个 API Key，调用 DeepSeek、GLM、Kimi、Qwen、MiniMax、GPT Image、Seedance 和 Jev。**

TokenRa 是独立运营、兼容 OpenAI 协议的 AI API 网关。任何 OpenAI SDK 只要把地址换成 `https://tokenra.io/v1` 就能用，换模型只改一个字符串。按量计费，无需订阅。

[官网](https://tokenra.io/zh/) · [获取 API Key](https://tokenra.io/register) · [模型与价格](https://tokenra.io/zh/models.html) · [开发文档](https://tokenra.io/zh/docs.html) · [示例代码](https://github.com/tokenra/tokenra-api-examples)

**最新动态：** 🆓 [MiniMax M3.1 Flash](https://tokenra.io/zh/models/minimax-m3.1-flash-api.html) 在 TokenRa 限时免费至 2026 年 10 月 31 日 · 🧠 [DeepSeek V4.1 Flash 1017](https://tokenra.io/zh/models/deepseek-v4.1-flash-1017.html) 已上线 · 🎯 [Jev](https://tokenra.io/zh/models/jev-api.html) 直接返回结构化判断，而不是一段文字

### 从这里开始

| 你需要什么 | 链接 | 用途 |
| --- | --- | --- |
| API Key | [注册获取](https://tokenra.io/register) | 一个 Key 调用所有已开通的模型 |
| 示例代码 | [tokenra-api-examples](https://github.com/tokenra/tokenra-api-examples) | cURL、Python、Node.js、Go：对话、流式、工具调用、识图、生图、视频、Jev |
| 模型目录 | [模型与价格](https://tokenra.io/zh/models.html) | 模型 ID、开发商和实时价格 |
| 开发文档 | [文档](https://tokenra.io/zh/docs.html) | 鉴权、接口地址和请求格式 |
| 框架接入 | [integrations](https://github.com/tokenra/tokenra-api-examples/tree/main/integrations) | LangChain、Vercel AI SDK、Claude Code、OpenCode |
| 数据处理 | [零数据留存说明](https://tokenra.io/zh/zero-data-retention.html) | TokenRa 如何处理请求内容 |

### 快速上手

```bash
curl https://tokenra.io/v1/chat/completions \
  -H "Authorization: Bearer $TOKENRA_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "deepseek-v4.1-flash",
    "messages": [{"role": "user", "content": "你好！"}]
  }'
```

已经在用 OpenAI SDK？只需替换 `base_url` 和 Key，其余代码不用改。更多语言和场景见 [示例仓库](https://github.com/tokenra/tokenra-api-examples)。
