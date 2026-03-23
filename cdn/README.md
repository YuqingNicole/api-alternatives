# CDN 替代方案（Cloudflare）

**Last updated: 2026-03-23**

## 现状

Cloudflare 免费 CDN 层覆盖了大多数小项目需求。寻找替代的场景主要是：需要更低延迟的流媒体、企业级 SLA、或更低成本的纯 CDN。

---

## 推荐方案对比

| 方案 | 价格/GB | PoPs | Edge Compute | 适合场景 |
|------|--------|------|-------------|---------|
| **Cloudflare** | 免费（基础）/ $20/月起 | 330+ | Workers（JS） | 全能，免费层极好 |
| **Bunny.net** ✅ 最便宜 | $0.01/GB | 125+ | 有 | 纯 CDN 降本，$1/月起 |
| **Fastly** | 企业定价 | 大型 PoP | Compute@Edge | 实时内容、低延迟流媒体 |
| Amazon CloudFront | $0.085/GB | 600+ | Lambda@Edge | AWS 生态集成 |
| KeyCDN | $0.04/GB | 50+ | 基础 | 中小项目，简单定价 |
| Akamai | 企业定价 | 365,000+ | EdgeWorkers | 超大规模企业 |

---

## 成本对比（1TB 流量/月）

| 方案 | 月成本 |
|------|--------|
| Cloudflare（基础免费） | $0 |
| Bunny.net | **$10** |
| KeyCDN | $40 |
| Amazon CloudFront | $85 |
| Fastly | 企业报价 |

---

## 选择指南

```
小/中流量，全能方案 → Cloudflare（免费层够用）
大流量，纯 CDN 降本 → Bunny.net（$0.01/GB，最便宜）
AWS 生态 → CloudFront
实时低延迟流媒体 → Fastly
超大型企业（10TB+/月）→ Akamai
```
