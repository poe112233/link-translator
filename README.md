# 微店转链工具 (link-translator)

把微店商品原始链接，一键批量转换成多个代购/转运渠道的可下单链接。

## 线上地址

🔗 **https://71172d9e502a493fb0b2d4ac941d74e8.app.workbuddy.link**

## 功能

- 支持**多行批量**输入微店原始链接，每行一个
- 自动提取链接中的 `itemID`
- 一次生成 **3 个渠道**的转链结果：
  | 渠道 | 生成规则 |
  |---|---|
  | Oopbuy | `https://oopbuy.com/product/weidian/{itemID}?originKeywordUrl={encode(encode(url))}` |
  | Kakobuy | `https://item.kakobuy.com/item/details?url={encode(url)}` |
  | Uidbuy | `https://www.uidbuy.com/product/3/{itemID}` |
- 每条链接可单独复制
- 一键复制 **TSV 表格**（Tab 分隔），可直接粘贴到 Excel / 飞书表格

## 使用方式

1. 打开线上地址（或本地直接双击 `index.html`）
2. 在输入框粘贴微店原始链接，一行一个
3. 点「生成转链」
4. 逐条复制，或点「复制表格」批量取走

## 项目结构

```
link-translator/
├── index.html   # 单文件应用（HTML + CSS + JS，无依赖）
└── README.md
```

## 技术说明

- 纯静态单文件，零依赖、零构建，可直接部署到任意静态托管
- 复制功能优先使用 `navigator.clipboard`，失败时回退到 `execCommand('copy')`
- 链接编码对 Oopbuy 采用**双重 encodeURIComponent**，符合其参数要求

## 更新记录

- 2026-09-11 初始化版本：多行批量转链、三渠道生成、单独复制、TSV 表格复制
