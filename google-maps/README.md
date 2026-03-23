# Google Maps API 替代方案

**Last updated: 2026-03-23**

## 现状

Google Maps 在 2025-03 重新定价，移除每月 $200 固定信用额，改为按 SKU 计费。Dynamic Maps $7/1K 次加载，Geocoding $5/1K 次请求。小流量场景有免费额度，大流量成本显著。

---

## 推荐方案对比

| 方案 | 地图加载/1K | Geocoding/1K | 免费层 | 适合场景 |
|------|-----------|-------------|--------|---------|
| **Google Maps** | $7 | $5 | 10K/月地图加载 | POI 数据最全，Street View |
| **Mapbox** ✅ | $5 | $0.75 | 50K/月加载 | 自定义样式，大流量降本 |
| **Radar** ✅ | 更低 | 更低 | 有 | 企业地理围栏，比 Google 省 50–90% |
| MapAtlas | $1.75 | - | 10K/月 | 纯成本优先 |
| OpenStreetMap + Leaflet | 免费 | 免费 | 无限制（自托管） | 预算极紧，可接受自托管 |
| HERE Maps | $0.50–$5/1K tiles | 按 tier | 30K tiles/月 | 企业物流/车载 |

---

## 选择指南

```
需要 Street View 或 Google Places 数据？
  → Google Maps（无可替代）

需要自定义地图样式 + 大流量？
  → Mapbox（50K 免费 + $5/1K，比 Google 便宜约 30%）

预算极紧，可接受较少 POI？
  → OpenStreetMap + Leaflet（免费，自托管 tiles）

企业级，需要 SLA + 地理围栏？
  → Radar（比 Google 便宜 50-90%）
```

---

## 成本对比示例（100K 地图加载/月）

| 方案 | 月成本 |
|------|--------|
| Google Maps | ~$630（10K 免费 + 90K × $7） |
| Mapbox | ~$250（50K 免费 + 50K × $5） |
| MapAtlas | ~$158（10K 免费 + 90K × $1.75） |
| OpenStreetMap | $0（自托管）|
