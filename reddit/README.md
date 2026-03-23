# Reddit API 替代方案

**Last updated: 2026-03-23**

## 现状

2023 年 Reddit 大幅涨价，2025 年持续收紧。官方免费层限制为 100 req/min，商业访问 $0.24/1,000 次调用。大量第三方客户端（Apollo 等）因此关闭。

---

## 推荐方案对比

| 方案 | 成本 | 实时 | 历史 | 适合场景 |
|------|------|------|------|---------|
| **PRAW**（官方封装）✅ | 免费（受速率限制） | ✅ | ✅ | Python 开发者，中小规模 |
| **Comment Exporter**（浏览器扩展）✅ | 免费（Reddit 部分）/ $5/月全平台 | ✅ | - | 非技术用户，一次性数据导出 |
| Xpoz | $0 免费层 / $20–200/月 | ✅ | ✅ | 多平台研究，自然语言查询 |
| Apify Reddit Scraper | $49+/月 | ✅ | - | 自定义工作流，企业 |
| Pushshift / PullPush | 免费（限制多） | ❌ | ✅ | 历史数据研究，学术 |
| 官方 Reddit API | $0.24/1K 调用 | ✅ | ✅ | 生产应用，需要官方合规 |

---

## PRAW 详情

- **官网**: https://praw.readthedocs.io
- Python Reddit API Wrapper，官方支持
- 免费，但速率限制：约 60 req/min（OAuth 认证后）
- 适合构建 bot、监控服务、数据管道

```python
import praw
reddit = praw.Reddit(client_id="xxx", client_secret="xxx", user_agent="myapp")
for post in reddit.subreddit("SideProject").hot(limit=10):
    print(post.title, post.score)
```

---

## 成本对比（100K 条/月）

| 方案 | 月成本 |
|------|--------|
| 官方 Reddit API | ~$24 + 开发时间 |
| Xpoz 免费层 | $0 |
| PRAW | $0（受速率限制） |
| Apify | $49+ |
| Comment Exporter | 免费（Reddit 不限） |
