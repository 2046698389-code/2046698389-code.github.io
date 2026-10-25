# 站点（2 个页面，纯静态，无构建）

- 建立日期：2026-10-25
- 内容：落地页 + 第 1 篇文章，英文成稿，可直接上线
- 依赖：无。纯 HTML + CSS，不用 npm、不用打包

```
站点/
├── index.html                    落地页
├── bottle-deposit-shopify.html   第 1 篇（URL 就是关键词）
├── styles.css
├── sitemap.xml
├── robots.txt
└── README.md
```

---

## 一、上线（3 步，10 分钟）

1. 打开 <https://app.netlify.com/drop>
2. 把整个 `站点` 文件夹拖进去
3. 拿到一个 `xxx.netlify.app` 网址，能打开就算上线

> 想用 Vercel 也行：把文件夹推到 GitHub，Vercel 导入，框架选 "Other"，无需构建命令。
> 两个都免费。**先用最省事的方式拿到一个能打开的网址**，域名以后再换。

## 二、上线前必须替换的 3 处

| 位置 | 现在写的 | 换成 |
|---|---|---|
| `index.html` / `sitemap.xml` / `robots.txt` 里的 `YOURSITE` | `https://YOURSITE.vercel.app` | 你拿到的真实网址 |
| `index.html` 的 `#waitlist` 区块 | Tally 占位说明 | 你的 Tally 表单嵌入代码 |
| `bottle-deposit-shopify.html` 的 `#waitlist` 区块 | 同上 | 同上 |

**waitlist 怎么做**：<https://tally.so> 注册免费号 → 新建表单，只放一个字段（邮箱）+ 一句"你在哪个市场卖瓶装饮料？" → 右上角 Share → Embed → 复制 iframe 代码 → 替换占位区块。5 分钟。

## 三、上线后立刻做（15 分钟）

1. <https://search.google.com/search-console> → 添加资源 → 网址前缀 → 填你的网址
2. 验证方式选「HTML 标记」，把 `<meta>` 粘进两个页面的 `<head>`
3. 左侧「站点地图」→ 提交 `你的网址/sitemap.xml`
4. <https://www.bing.com/webmasters> 同样做一遍（Bing 收录快，且 ChatGPT 用 Bing 索引）

## 四、这两页已经做好的 SEO/AEO 细节

- 每页 `<title>` 和 `<meta description>` 都是围绕一个搜索意图写的
- 落地页有 `SoftwareApplication` 结构化数据
- 文章有 `FAQPage` 结构化数据（3 条问答，AI 抓取时优先用这个）
- 标题层级只有 h1/h2/h3，没有跳级
- 无外部字体、无 JS、无跟踪脚本 → 加载快，Core Web Vitals 无风险
- `canonical` 已设，以后换 .com 时逐页 301 即可

## 五、三篇文章的剩余进度

| 篇 | 状态 | 目标词 |
|---|---|---|
| 1 `bottle-deposit-shopify` | ✅ 已成稿 | `shopify bottle deposit`、`how to charge bottle deposit` |
| 2 `ireland-drs-shopify` | 待写 | `ireland deposit return shopify`、`DRS shopify` |
| 3 `bottle-deposit-apps-compared` | 待写 | `shopify bottle deposit app`（意图最高） |

## 六、维护规则

- 每周只改一件事：加一篇新页面（复制 `bottle-deposit-shopify.html` 改内容，文件名就是新关键词）
- 每次改完，把新 URL 加进 `sitemap.xml`
- 页面里的押金金额永远写"以官方为准"，不要写死，避免过时
