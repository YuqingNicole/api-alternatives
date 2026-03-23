# AI / LLM API 替代方案（OpenAI GPT）

**Last updated: 2026-03-23**

## 定价对比（2026-03）

| 提供商 | 模型 | Input/1M tokens | Output/1M tokens | 上下文窗口 | 特点 |
|--------|------|----------------|-----------------|-----------|------|
| OpenAI | gpt-5 | $5 | $25 | 128K | 生态最成熟 |
| **Anthropic** ✅ | claude-opus-4.5 | $2.5 | $12.5 | 200K | 推理/代码更强 |
| **Google** ✅ | gemini-2.5-pro | $1.25–$2.5 | $5–$15 | 2M | 多模态/长上下文 |
| Meta | llama-3.3-70b | $0.60 | $0.60 | 128K | 开源，可自托管 |
| DeepSeek | deepseek-v3 | ~$0.14 | ~$0.28 | 64K | 成本最低，中文强 |
| Mistral | mistral-large | $2 | $6 | 128K | 欧洲合规，多语言 |

---

## 选择指南

```
代码/推理任务 → Claude Opus 4.5
多模态/超长上下文 → Gemini 2.5 Pro（2M context）
预算优先（高并发） → DeepSeek / Llama 3.3（自托管）
欧洲数据合规 → Mistral
生产级 + 最全生态 → OpenAI GPT-5（贵但文档最全）
```

---

## 成本示例（1M tokens 每月）

| 方案 | 月费（input+output各50%） |
|------|--------------------------|
| GPT-5 | $15 |
| Claude Opus 4.5 | $7.5 |
| Gemini 2.5 Pro | ~$3.75 |
| DeepSeek | ~$0.21 |

---

## API 统一入口（避免 vendor lock-in）

- **LiteLLM** — 统一接口调用 100+ 模型，本地部署
- **OpenRouter** — 统一 API key，按模型计费，支持所有主流模型
- **Crazyrouter** — OpenAI 兼容接口，一键切换模型

```python
# LiteLLM 示例：切换模型只改一行
from litellm import completion
response = completion(model="anthropic/claude-opus-4.5", messages=[...])
response = completion(model="gemini/gemini-2.5-pro", messages=[...])  # 同一接口
```
