# Resend-Online

基于 Resend API 的在线邮件发送工具

## 技术栈
- 前端：Vue 3 + Vite + Tailwind CSS
- 后端：Cloudflare Workers
- 邮件服务：Resend API

## 架构
- 前后端分离
- 无状态设计（API key 不存储）
- 全球边缘部署

## 目录结构
- `frontend/` - Vue 3 应用
- `worker/` - Cloudflare Worker API

## 功能特性
- 基础文本/HTML 邮件发送
- 附件上传支持
- 抄送/密送（CC/BCC）
- 实时发送状态反馈

## 本地开发

### 前置要求
- Node.js 18+
- pnpm 8+
- Wrangler CLI

### 后端（Worker）
```bash
cd worker
pnpm install
pnpm dev  # 启动在 http://localhost:8787
```

### 前端（Vue）
```bash
cd frontend
pnpm install
pnpm dev  # 启动在 http://localhost:5173
```

## 部署

### 部署 Worker
```bash
cd worker
wrangler login
wrangler deploy
```

### 部署前端（Cloudflare Pages）
```bash
cd frontend
pnpm build
wrangler pages deploy dist
```

## 环境变量

Worker 需要配置 `.dev.vars`（本地开发）或通过 Wrangler 设置环境变量（生产环境）。

## 安全说明

- API key 仅在请求体中传输，不存储在服务端
- 每次发送邮件需要重新输入 API key
- 建议在生产环境使用 HTTPS
