# xihe-search-forge

SEO + AEO + GEO 一站式搜索优化锻造炉。

一个命令审计你的网站在传统搜索引擎和 AI 搜索引擎中的可见性，给出可执行的优化建议。

> v0.3 · 11 工具 · 5 AI 引擎 · 48 tests · by [xihe-forge](https://github.com/xihe-forge)

---

## 快速开始

```bash
# npx（无需安装）
npx xihe-search-forge --url https://yoursite.com

# 或 clone 后使用
git clone https://github.com/xihe-forge/xihe-search-forge.git
cd xihe-search-forge && pnpm install
npm run audit -- --url https://yoursite.com --brand "YourBrand"
```

---

## 审计输出

一次运行覆盖 7 个维度：

| 维度 | 数据来源 | 免费 |
|------|---------|------|
| SEO 技术基线 | Google Lighthouse | ✅ |
| 页面信号（Meta/Schema/FAQ/链接） | 内置爬虫 | ✅ |
| GEO 内容优化建议 | Princeton 论文量化模型 | ✅ |
| 平台存在度（Reddit/YouTube/Wikipedia...） | 8 大平台 API | ✅ |
| 内容新鲜度 | Sitemap + 页面日期信号 | ✅ |
| AI 引用检测 + 品牌情感 | Perplexity / ChatGPT / Gemini / Kimi / You.com | 需 API Key |
| AI 声量占比 vs 竞品 | 同上 | 需 API Key |

---

## 工具一览

| # | 工具 | 命令 | 说明 |
|---|------|------|------|
| 0 | **一键全套** | `npm run audit` | 运行以下全部，输出综合报告 |
| 1 | Lighthouse | `npm run lighthouse` | Google SEO 技术基线 |
| 2 | 页面爬取 | `npm run crawl` | SEO/AEO/GEO 信号提取 |
| 3 | AI 引用检测 | `npm run citation` | 5 引擎 + 情感 + 竞品 |
| 4 | llms.txt 生成 | `npm run llms-txt` | AI 爬虫引导文件 |
| 5 | GSC 数据 | `npm run gsc` | Google Search Console |
| 6 | 内容优化 | `npm run content-optimize` | Princeton GEO 论文建议 |
| 7 | 平台存在度 | `npm run platform-presence` | 8 大高引用平台 |
| 8 | 声量占比 | `npm run share-of-voice` | 你 vs 竞品引用率 |
| 9 | 内容新鲜度 | `npm run freshness` | 标记过期页面 |
| 10 | 负面 GEO 防御 | `npm run negative-geo` | 情感突变 + 协同攻击 |

📖 各工具详细用法和参数：[docs/tools.md](docs/tools.md)

---

## Claude Code Skills

```bash
# 安装全部 skills
cp -r skills/*/ ~/.claude/skills/
```

| 命令 | 功能 |
|------|------|
| `/search-forge` | **一键全套审计** |
| `/search-forge:seo` | SEO 审计 |
| `/search-forge:aeo` | AEO 审计（8 维度） |
| `/search-forge:citation` | AI 引用监测 |
| `/search-forge:content` | GEO 内容优化 |
| `/search-forge:presence` | 平台存在度 |
| `/search-forge:freshness` | 内容新鲜度 |
| `/search-forge:voice` | 声量占比 |
| `/search-forge:defense` | 负面 GEO 防御 |
| `/search-forge:report` | 前后对比报告 |

---

## 反馈闭环

```
/search-forge（基线） → 优化 → /search-forge（复查） → /search-forge:report（对比） → ...
```

---

## API Key 配置

AI 引用检测相关功能需要至少一个 API Key：

```bash
export PERPLEXITY_API_KEY=pplx-xxxx    # perplexity.ai/settings/api
export OPENAI_API_KEY=sk-xxxx          # platform.openai.com/api-keys
export GEMINI_API_KEY=AIza-xxxx        # aistudio.google.com/app/apikey
export MOONSHOT_API_KEY=sk-xxxx        # platform.moonshot.cn
export YOU_API_KEY=xxxx                # you.com/api
```

无 API Key 时，Lighthouse / 爬虫 / 内容优化 / 平台存在度 / 新鲜度检测仍可正常使用。

---

## License

MIT — by [xihe-forge](https://github.com/xihe-forge)
