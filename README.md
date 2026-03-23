# API Alternatives Tracker

> 实时追踪常用 API 的替代方案、定价变化和最新动态。适合独立开发者和小团队在官方 API 涨价/限制时快速找到替代。

**Last updated: 2026-03-23 | 8 个类别**

---

## 索引

| 类别 | 推荐替代 | 最近重大变更 | 文档 |
|------|---------|------------|------|
| [LinkedIn](#) | Proxycurl | 官方 API 仍高门槛 | [→](linkedin/README.md) |
| [Twitter / X](#) | GetXAPI / Tweapi | 2023 涨价，2026 彻底无免费层 | [→](twitter/README.md) |
| [Reddit](#) | PRAW + 浏览器扩展 | 2023 大幅涨价，2025 持续收紧 | [→](reddit/README.md) |
| [Google Maps](#) | Mapbox / Radar | 2025-03 重新定价，移除 $200 固定额度 | [→](google-maps/README.md) |
| [Email（SendGrid）](#) | Resend / Amazon SES | 2025-05 免费层彻底取消 | [→](email/README.md) |
| [AI / LLM（OpenAI）](#) | Claude / Gemini / DeepSeek | 价格持续下降，竞争激烈 | [→](ai-llm/README.md) |
| [Web Scraping（Apify）](#) | Firecrawl / Zyte | AI-native 抓取方案崛起 | [→](web-scraping/README.md) |
| [通信（Twilio）](#) | Vonage / Sinch | 持续涨价，DX 老化 | [→](twilio/README.md) |

---

## 贡献

发现 API 有新变更或更好的替代方案？直接提 PR：
- 更新对应目录的 `README.md`（方案对比）
- 在 `changelog.md` 追加变更记录（带日期）

---

## 变更追踪原则

1. 每次 API 有重大定价/政策变化，在对应 `changelog.md` 记录
2. `README.md` 只保留**当前推荐**，不做历史方案存档
3. 对比表数据来源需注明日期，过期数据及时更新
