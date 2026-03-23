# Email API 替代方案（SendGrid / Twilio SendGrid）

**Last updated: 2026-03-23**

## 现状

SendGrid 自 2025-05 彻底移除免费层，现仅提供 60 天试用（100 封/天上限）。Twilio 收购后涨价、体验停滞，大量团队迁移中。

---

## 推荐方案对比

| 方案 | 月费 | 免费层 | 适合场景 |
|------|------|--------|---------|
| **Resend** ✅ 开发者首选 | $20/月起（50K 封） | 3,000 封/月 | 现代 DX，React Email，API-first |
| **Amazon SES** ✅ 大规模首选 | $0.10/1K 封 | 62K/月（从 EC2 发） | 极低成本，AWS 用户 |
| **Postmark** ✅ 高送达率 | $15/月（10K 封） | 100 封/月 | 事务邮件，99%+ 收件率 |
| Mailgun | $15/月（10K 封） | 100 封/天（试用） | 最接近 SendGrid 的替代 |
| Brevo（前 Sendinblue） | $9/月（5K 封） | 300 封/天 | 事务 + 营销一体化 |
| Emailit | $44 一次性 | — | 预算极紧，20K 封/月买断 |

---

## 成本对比（50K 封/月）

| 方案 | 月成本 |
|------|--------|
| SendGrid | ~$89.95 |
| Resend | $20 |
| Amazon SES | $5 |
| Postmark | $74 |
| Mailgun | $80 |

---

## Resend 详情

- **官网**: https://resend.com
- 前 SendGrid 工程师创立，API 设计更现代
- 支持 React Email 组件
- 3,000 封/月免费，适合早期产品

```bash
curl -X POST https://api.resend.com/emails \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"from":"you@example.com","to":["user@example.com"],"subject":"Hello","html":"<p>Hi</p>"}'
```

---

## 选择指南

- **高流量 + 预算优先** → Amazon SES（$0.10/1K）
- **现代开发体验** → Resend
- **事务邮件送达率优先** → Postmark
- **营销 + 事务一体** → Brevo
- **一次性买断** → Emailit（适合 < 100K/月）
