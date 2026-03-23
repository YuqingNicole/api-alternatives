# LinkedIn API 替代方案

**Last updated: 2026-03-23**

## 现状

LinkedIn 官方 API 门槛极高，个人/小团队基本拿不到完整权限。需要申请 Marketing Developer Platform 或成为合作伙伴，审核周期长。

---

## 推荐方案对比

| 方案 | 稳定性 | 成本 | 上手速度 | 适合场景 |
|------|--------|------|---------|---------|
| **Proxycurl** ✅ 推荐 | ⭐⭐⭐⭐⭐ | $0.01–0.05/请求 | 快 | 产品集成，生产环境 |
| RapidAPI | ⭐⭐⭐ | 更低，按套餐 | 快 | MVP 测试阶段 |
| 官方 LinkedIn API | ⭐⭐⭐⭐⭐ | 免费（但难拿） | 慢（需审核） | 大公司，合规要求高 |
| PhantomBuster / Apify | ⭐⭐ | 月费 $56+ | 中等 | ⚠️ 不推荐，封号风险 |

---

## Proxycurl 详情

- **官网**: https://proxycurl.com
- **功能**: 个人资料、公司信息、搜索、联系方式（Company Search API）
- **有 SLA 保证**，适合生产环境集成
- **计费**: 按请求量，无月费起步

```bash
# 示例：查公司信息
curl -G https://nubela.co/proxycurl/api/linkedin/company \
  -H "Authorization: Bearer YOUR_API_KEY" \
  --data-urlencode "url=https://www.linkedin.com/company/google/"
```

---

## 场景建议

**B2B Outbound（如 Sitesfy）推荐执行路径**:
```
Apollo 拉名单 → Proxycurl 补决策人 → Instantly 发邮件序列
```

- Apollo 覆盖面广，Proxycurl 在找具体负责人时更精准
- LinkedIn 渠道本身建议延后，先跑邮件验证 ICP
