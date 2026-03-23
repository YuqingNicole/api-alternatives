# API Alternatives Tracker

> 实时追踪常用 API 的替代方案、定价变化和最新动态。适合独立开发者和小团队在官方 API 涨价/限制时快速找到替代。

**Last updated: 2026-03-23 | 13 个类别**

---

## 索引

| 类别 | 推荐替代 | 最近重大变更 | 文档 |
|------|---------|------------|------|
| **数据获取** | | | |
| LinkedIn | Proxycurl | 官方 API 仍高门槛 | [→](linkedin/README.md) |
| Twitter / X | GetXAPI / Tweapi | 2026 彻底无免费层 | [→](twitter/README.md) |
| Reddit | PRAW + 浏览器扩展 | 2023 涨价，2025 收紧 | [→](reddit/README.md) |
| Web Scraping（Apify） | Firecrawl / Zyte | AI-native 抓取方案崛起 | [→](web-scraping/README.md) |
| **基础设施** | | | |
| 对象存储（AWS S3） | Cloudflare R2 / Backblaze B2 | R2 零 egress 费用颠覆市场 | [→](storage/README.md) |
| CDN（Cloudflare） | Bunny.net | $0.01/GB，最便宜纯 CDN | [→](cdn/README.md) |
| Google Maps | Mapbox / Radar | 2025-03 重新定价 | [→](google-maps/README.md) |
| **应用服务** | | | |
| 支付（Stripe） | Paddle / Lemon Squeezy | Stripe MoR 私测 +3.5% 费 | [→](stripe/README.md) |
| 认证（Auth0） | Clerk / Supabase Auth | Okta 整合后涨价 | [→](auth/README.md) |
| 搜索（Algolia） | Typesense / Meilisearch | 开源替代方案成熟 | [→](search/README.md) |
| Email（SendGrid） | Resend / Amazon SES | 2025-05 免费层取消 | [→](email/README.md) |
| 通信（Twilio） | Vonage / Sinch | 持续涨价 | [→](twilio/README.md) |
| **AI / 数据** | | | |
| AI / LLM（OpenAI） | Claude / Gemini / DeepSeek | 价格持续下降 | [→](ai-llm/README.md) |

---

## 贡献

发现 API 有新变更或更好的替代方案？直接提 PR：
- 更新对应目录的 `README.md`（方案对比）
- 在 `changelog.md` 追加变更记录（带日期）

---

## 变更追踪原则

1. 每次 API 有重大定价/政策变化 → 更新 `changelog.md`
2. `README.md` 只保留**当前推荐**，不做历史方案存档
3. 对比表数据需注明来源日期，过期及时更新
