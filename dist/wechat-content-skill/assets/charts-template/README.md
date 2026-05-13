# 图表 HTML 模板

这个目录是图表 HTML 的最小可运行示例，包含：

```
charts-template/
├── example.html       # 示例 HTML (2 张图)
└── lib/               # 离线 JS 库 (3.7MB)
    ├── react.production.min.js
    ├── react-dom.production.min.js
    ├── prop-types.min.js
    ├── recharts.js
    └── babel.min.js
```

## 怎么用

**方式 1：直接体验**
- 双击 `example.html`，浏览器打开后看到 2 张图（折线 + 柱状）

**方式 2：作为新文章的起点**

把这个 `charts-template/` 目录拷到你的项目 `articles/配图/`：

```bash
cp -r charts-template ~/your-project/articles/配图/
# 然后改名为你的文章 slug
mv ~/your-project/articles/配图/charts-template/example.html ~/your-project/articles/配图/your-article-name.html
# lib/ 留在 articles/配图/lib/,所有文章共用
```

## 如果 lib/ 丢失了

```bash
mkdir -p lib && cd lib
curl -sSL -o react.production.min.js     https://unpkg.com/react@18/umd/react.production.min.js
curl -sSL -o react-dom.production.min.js https://unpkg.com/react-dom@18/umd/react-dom.production.min.js
curl -sSL -o prop-types.min.js           https://unpkg.com/prop-types@15.8.1/prop-types.min.js
curl -sSL -o recharts.js                 https://unpkg.com/recharts@2.12.0/umd/Recharts.js
curl -sSL -o babel.min.js                https://unpkg.com/@babel/standalone/babel.min.js
```

## 为什么不用 Tailwind CDN

`https://cdn.tailwindcss.com` 是运行时 JIT 编译，需要联网，并且在 `file://` 协议下经常被浏览器拦截。本模板把 Tailwind 替换成手写内联 CSS，保证完全离线、双击可用。
