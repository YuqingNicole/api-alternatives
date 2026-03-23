# 支付 API 替代方案（Stripe）

**Last updated: 2026-03-23**

## 现状

Stripe 是开发者首选支付 API，但 2.9% + $0.30/笔的标准费率在规模化后成本显著，税务合规也需自行处理。MoR（Merchant of Record）方案正在兴起。

---

## 两种路径

**路径 A：纯支付网关**（类似 Stripe，需自行处理税务）
**路径 B：MoR（Merchant of Record）**（全权代管税务合规）

---

## 推荐方案对比

| 方案 | 费率 | MoR | 全球税务 | 适合场景 |
|------|------|-----|---------|---------|
| **Stripe** | 2.9% + $0.30 | 测试中（+3.5%） | 需自理 | 开发者体验最佳，生态最全 |
| **Paddle** ✅ SaaS 首选 | ~5% | ✅ | ✅ 自动 | SaaS 跨国销售，自动 VAT/GST |
| **Lemon Squeezy** ✅ 独立开发者 | 5% + $0.50 | ✅ | ✅ | 数字产品，独立开发者 |
| **Polar** ✅ 开发者工具 | 4% + $0.40 | ✅ | ✅ | 开发者产品，开源友好 |
| Adyen | 按量，无固定费率 | ❌ | ❌ | 大企业，跨渠道全球支付 |
| GoCardless | 低（直接借记） | ❌ | ❌ | 订阅/重复收款，欧洲市场 |
| Braintree（PayPal） | 2.9% + $0.30 | ❌ | ❌ | 需要 PayPal 集成 |

---

## 选择指南

```
个人/独立开发者卖数字产品 → Lemon Squeezy / Polar（MoR，免税务烦恼）
SaaS 跨国销售（需处理 VAT/GST） → Paddle（最成熟的 MoR）
需要 PayPal 集成 → Braintree
大规模全球支付，企业级 → Adyen
欧洲订阅/直接借记 → GoCardless
自定义开发，接受税务自理 → Stripe（API 最好）
```

---

## 注意

Stripe MoR 功能（2026 年在测试阶段）将额外收取 **3.5%**，相比 Paddle/Lemon Squeezy 仍偏贵。
