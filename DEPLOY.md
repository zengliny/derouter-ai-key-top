# derouter.ai-key.top 引流网站部署指南

## 项目文件

本项目已创建以下文件：
- `index.html` - 主页面（仿 derouter.ai 设计）
- `styles.css` - 样式文件
- `_routes.json` - Cloudflare Pages 配置

## 部署方式（三选一）

### 方式一：Cloudflare Pages Dashboard（推荐，最简单）

1. **登录 Cloudflare Dashboard**
   - 访问 https://dash.cloudflare.com
   - 登录你的账号

2. **创建 Pages 项目**
   - 左侧菜单点击 **Workers & Pages** → **Create application**
   - 选择 **Pages** 标签
   - 点击 **Connect to Git** 或 **Direct upload**（直接上传）

3. **直接上传部署**
   - 选择 **Direct upload**
   - 将 `derouter-clone` 文件夹内的所有文件拖拽到上传区域
   - 点击 **Deploy**

4. **绑定自定义域名**
   - 部署完成后，进入项目设置
   - 点击 **Custom domains**
   - 添加域名：`derouter.ai-key.top`
   - 按照提示配置 DNS（Cloudflare 会自动处理）

### 方式二：使用 Wrangler CLI

```bash
# 安装 Wrangler
npm install -g wrangler

# 登录 Cloudflare
wrangler login

# 进入项目目录
cd derouter-clone

# 创建项目
wrangler pages project create derouter-clone

# 部署
wrangler pages publish .
```

### 方式三：使用 Cloudflare Pages GitHub 集成

1. 将此项目推送到 GitHub
2. 在 Cloudflare Dashboard 中连接 GitHub 仓库
3. 设置自动部署（每次 push 自动构建）

## DNS 配置

在 Cloudflare DNS 设置中添加：

| 类型 | 名称 | 内容 | Proxy |
|------|------|------|-------|
| CNAME | derouter.ai-key.top | <your-project>.pages.dev | Proxied |

## 项目特点

✅ **完全静态** - 无需后端，纯 HTML/CSS
✅ **免费托管** - Cloudflare Pages 免费额度足够
✅ **全球 CDN** - 自动加速，访问速度快
✅ **自动 HTTPS** - 免费 SSL 证书
✅ **无限带宽** - 无流量限制

## 自定义建议

1. **修改推荐链接** - 所有 `href="https://derouter.ai?ref=AI-KEY-TOP"` 已是你的推荐链接
2. **添加统计** - 可添加 Google Analytics 或 Umami 追踪访问
3. **SEO 优化** - 已包含基础 meta 标签，可根据需要调整
4. **颜色定制** - 修改 `styles.css` 中的 CSS 变量调整主题色

## 后续优化

- 添加 favicon.ico
- 添加 Open Graph 图片（用于社交媒体分享）
- 添加 statisitcs 统计代码
- 多语言支持（英文版本）
