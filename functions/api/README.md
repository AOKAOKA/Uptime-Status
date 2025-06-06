# API 目录说明

本目录 (`functions/api/`) 包含了 腾讯云 EdgeOne Pages 和 Cloudflare Pages 的 API 代理实现。

## 文件说明

### status.js

这是一个运行在边缘节点上的代理函数，主要用于：
- 转发请求到 UptimeRobot API
- 处理 CORS（跨域）请求
- 处理错误响应

## 请求处理

1. OPTIONS 请求：返回 CORS 头部
2. POST 请求：转发到 UptimeRobot API
3. 错误处理：返回统一的错误响应

## 环境变量配置

在项目根目录的 `.env` 文件中配置：

```bash
# API 代理地址
VITE_UPTIMEROBOT_API_URL = "/api/status"  # 使用默认配置
```

## 部署说明

- 支持多个平台部署:
  - 腾讯云 EdgeOne Pages
  - Cloudflare Pages
- 路由 `/api/status` 由平台自动处理
- 不需要额外的路径检查或路由配置

请确保在部署前正确配置环境变量，以保证 API 请求能够正常工作。 