# 认证 API 替代方案（Auth0）

**Last updated: 2026-03-23**

## 现状

Auth0 被 Okta 收购后价格大幅上涨，免费层仅 7,500 MAU。Clerk、Supabase Auth 等现代替代方案成本更低、DX 更好。

---

## 推荐方案对比

| 方案 | 免费层 | 起步付费 | 自托管 | 适合场景 |
|------|--------|---------|--------|---------|
| **Clerk** ✅ 首选 | 10,000 MAU | $25/月 | ❌ | 现代 DX，Next.js/React 最佳集成 |
| **Supabase Auth** ✅ | 50,000 MAU | $25/月（含全套） | ✅ | 全栈开源，PostgreSQL + Auth 一体 |
| **Better Auth** ✅ 开源 | 无限（自托管） | 免费 | ✅ | TypeScript 原生，最新开源方案 |
| Auth0 | 7,500 MAU | $23/月 | ❌ | 企业合规要求，复杂权限体系 |
| Firebase Auth | 无限 | 免费（Google 生态） | ❌ | Google 生态，移动端 |
| NextAuth.js / Auth.js | 无限（自托管） | 免费 | ✅ | Next.js 项目，简单集成 |
| WorkOS | 100 MAU | $49/月 | ❌ | 企业 SSO（SAML/SCIM） |

---

## Clerk 详情

- **官网**: https://clerk.com
- 10,000 MAU 免费，超出 $0.02/MAU
- 内置 UI 组件（登录/注册页，直接嵌入）
- Next.js、React、Expo 深度集成

```tsx
// Next.js 示例
import { SignIn } from "@clerk/nextjs";
export default function Page() { return <SignIn />; }
```

---

## Supabase Auth 详情

- **官网**: https://supabase.com
- 50,000 MAU 免费（含 Database、Storage、Edge Functions）
- PostgreSQL RLS（行级安全）原生集成
- 开源可自托管

---

## 选择指南

```
Next.js / React 项目 → Clerk（UI 组件开箱即用）
全栈开源项目 → Supabase（Auth + DB + Storage 一体）
企业 SSO（SAML/SCIM） → WorkOS
自托管，成本优先 → Better Auth / NextAuth.js
Firebase 生态 → Firebase Auth
```
