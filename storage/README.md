# 对象存储 API 替代方案（AWS S3）

**Last updated: 2026-03-23**

## 现状

AWS S3 是行业标准，但 egress（出口流量）费用 $0.09/GB 在大流量场景下成本高昂。多个 S3 兼容替代方案可节省 50-80%。

---

## 推荐方案对比（S3 兼容 API）

| 方案 | 存储/GB | Egress/GB | 免费层 | 适合场景 |
|------|--------|----------|--------|---------|
| **Cloudflare R2** ✅ 首选 | $0.015 | **$0（免费！）** | 10GB 永久 | 带宽密集型应用，零 egress 成本 |
| **Backblaze B2** ✅ 最便宜 | $0.006 | $0.01（>1TB） | 10GB 永久 | 备份/归档，最低存储价格 |
| **DigitalOcean Spaces** | $5/月 | 含 1TB | 250GB + 1TB 带宽 | 固定预算，含 CDN |
| AWS S3 | $0.023 | $0.09 | 5GB（12个月） | AWS 生态深度集成 |
| Google Cloud Storage | $0.020 | $0.12 | — | GCP 生态，BigQuery 分析 |
| MinIO | 免费（自托管） | 免费 | 无限 | 私有化部署，完全控制 |

---

## 成本对比（1TB 存储 + 1TB egress/月）

| 方案 | 月成本 |
|------|--------|
| AWS S3 | $113（$23 存储 + $90 egress）|
| Cloudflare R2 | $15（存储）+ $0 egress = **$15** |
| Backblaze B2 | $6（存储）+ $10 egress = $16 |
| DigitalOcean Spaces | $5（包含所有）|

---

## Cloudflare R2 详情

- **官网**: https://developers.cloudflare.com/r2
- S3 兼容 API，迁移代价极低（改 endpoint 即可）
- 零 egress 费用（包括与 Cloudflare CDN 集成）
- Workers + Pages 深度整合

```python
import boto3
s3 = boto3.client("s3",
    endpoint_url="https://ACCOUNT_ID.r2.cloudflarestorage.com",
    aws_access_key_id="R2_ACCESS_KEY",
    aws_secret_access_key="R2_SECRET_KEY"
)
# 代码完全兼容 S3 SDK
```

---

## 选择指南

```
带宽是主要成本 → Cloudflare R2（egress 免费）
纯存储/备份成本最低 → Backblaze B2（$0.006/GB）
固定月费，简单计费 → DigitalOcean Spaces（$5/月含 CDN）
AWS 生态深度绑定 → AWS S3
私有化部署 → MinIO（开源自托管）
```
