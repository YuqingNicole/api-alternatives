# 搜索 API 替代方案（Algolia）

**Last updated: 2026-03-23**

## 现状

Algolia 是全托管搜索 API 标杆，但价格昂贵（10K 请求/月免费，超出 $1/1K 请求）。Typesense、Meilisearch 等开源替代方案快速成熟。

---

## 推荐方案对比

| 方案 | 免费层 | 自托管 | 速度 | 适合场景 |
|------|--------|--------|------|---------|
| **Typesense** ✅ 首选 | 无限（自托管）/ Cloud $25/月起 | ✅ | 极快（Rust） | Algolia 直接替代，开源 |
| **Meilisearch** ✅ | 无限（自托管）/ Cloud $30/月起 | ✅ | 极快 | 简单配置，中文友好 |
| Algolia | 10K 请求/月 | ❌ | 极快 | 全托管，企业级 SLA |
| ElasticSearch | 无限（自托管） | ✅ | 快 | 复杂搜索需求，大规模日志 |
| OpenSearch | 无限（自托管）| ✅ | 快 | AWS 生态，ElasticSearch 替代 |

---

## Typesense 详情

- **官网**: https://typesense.org
- Rust 编写，毫秒级搜索
- 完全兼容 Algolia SDK（几乎零成本迁移）
- 自托管免费，Cloud 版 $25/月

```bash
# Docker 启动
docker run -p 8108:8108 -v /tmp/typesense-data:/data \
  typesense/typesense:27.0 --data-dir /data --api-key=xyz
```

---

## 成本对比（100K 请求/月）

| 方案 | 月成本 |
|------|--------|
| Algolia | ~$90+ |
| Typesense Cloud | ~$25 |
| Typesense 自托管 | $5–10（服务器费） |
| Meilisearch Cloud | ~$30 |

---

## 选择指南

```
Algolia 迁移成本最小 → Typesense（SDK 兼容）
需要中文/多语言支持 → Meilisearch
日志/大规模全文检索 → ElasticSearch / OpenSearch
预算为零，可自托管 → Typesense / Meilisearch（开源免费）
```
