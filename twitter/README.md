# Twitter / X API 替代方案

**Last updated: 2026-03-23**

## 现状

2023 年 Twitter/X 移除免费 API 访问层，2026 年进一步收紧，当前 Pro 计划 $5,000/月 才能读 100 万条推文。第三方替代方案成本约为官方的 1/100。

---

## 推荐方案对比

| 方案 | 成本 / 1K 推文 | 实时数据 | 历史数据 | 适合场景 |
|------|--------------|---------|---------|---------|
| **GetXAPI** ✅ 推荐 | ~$0.05 | ✅ | ✅ | 数据收集、研究、分析、bot |
| **Tweapi** ✅ 推荐 | 按信用点，约 $0.05–0.10 | ✅（毫秒级） | ✅ | 实时监控、AI 应用 |
| TwitterAPI.io | $0.15/1K | ✅ | ✅ | API 替换，读写都支持 |
| Bright Data | 企业定价 | ✅ | ✅ | 大规模企业场景 |
| 官方 X API v2 | $5–10/1K 推文 | ✅ | 7天内免费，全量 $42K+/月 | 需要 OAuth 用户授权的场景 |

---

## GetXAPI 详情

- **官网**: https://getxapi.com
- **比官方便宜约 100 倍**：官方 $10 ≈ 2,000 条推文，GetXAPI $10 ≈ 200,000 条
- 无需 Twitter OAuth，一个 Bearer token 直接调用
- 不支持用户授权流（如代用户发推）

```bash
curl -H "Authorization: Bearer YOUR_KEY" \
  "https://api.getxapi.com/twitter/tweet/advanced_search?q=openclaw"
```

---

## Tweapi 详情

- **官网**: https://tweapi.io
- 毫秒级实时流数据
- 免费 200 credits 试用，Starter $10/月约 71,428 条数据
- REST API，无需 Twitter 账号

---

## 注意

GetXAPI 和 Tweapi 均**不支持用户授权 OAuth**。如需代用户执行操作（发推、点赞、关注），仍需官方 API。
