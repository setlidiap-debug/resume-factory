# 简历工厂 · Resume Factory

一个帮你针对不同岗位快速生成定制简历的 AI 工具。
解决海投时"每份简历都要改"的痛点。

## 文件结构

```
resume-factory/
├── index.html      ← 整个工具，就这一个文件
├── vercel.json     ← Vercel 部署配置
└── README.md       ← 本文件
```

---

## 部署方式（任选其一）

### 方式 A：Vercel（推荐，最快）

1. 注册 [vercel.com](https://vercel.com)（GitHub 账号登录即可）
2. 点击 **Add New Project** → **Upload**
3. 把 `resume-factory` 文件夹整个拖进去
4. 点击 **Deploy**，等 30 秒
5. 得到一个 `xxx.vercel.app` 的链接，分享给任何人

---

### 方式 B：GitHub Pages（免费，适合长期维护）

1. 注册 [github.com](https://github.com)
2. 新建一个 Repository，名字随意（例如 `resume-factory`）
3. 把 `index.html` 上传到仓库
4. 进入仓库 **Settings → Pages**
5. Source 选择 **Deploy from a branch** → branch 选 `main`，folder 选 `/ (root)`
6. 保存，等 1 分钟，得到 `xxx.github.io/resume-factory` 链接

---

### 方式 C：Cloudflare Pages（速度最快，国内访问友好）

1. 注册 [pages.cloudflare.com](https://pages.cloudflare.com)
2. 新建项目 → **Direct Upload**
3. 拖入 `index.html`（和 `vercel.json` 可不传）
4. 点击 Deploy，得到 `xxx.pages.dev` 链接

---

## 用户使用说明

打开链接后，用户需要：

1. 在顶部填写自己的 **Anthropic API Key**
   - 去 [console.anthropic.com](https://console.anthropic.com/settings/keys) 注册并获取
   - 新用户有免费额度，生成一份简历大约消耗 $0.003（不到两分钱）
   - Key 只在本地浏览器使用，不经过任何服务器

2. 按三步走：
   - **步骤 1**：填写简历母版（一次性）
   - **步骤 2**：粘贴目标岗位 JD，AI 解析
   - **步骤 3**：选调性，生成定制简历

3. 海投时：母版只填一次，每次换 JD 重复步骤 2-3 即可

---

## 后续迭代计划

- [ ] 步骤 4：模拟面试（基于生成的简历 + JD 出面试题）
- [ ] 步骤 5：HR 打招呼生成器（针对 Boss 直聘等平台）
- [ ] 步骤 6：自动化海投（JD 批量处理）
- [ ] 本地存储母版（刷新页面不丢失）

---

## 技术说明

- 纯静态 HTML，无后端，无数据库
- 直接调用 Anthropic Claude API（claude-sonnet）
- 用户 API Key 仅存在浏览器内存，不上传任何服务器
- 支持流式输出（边生成边显示）
