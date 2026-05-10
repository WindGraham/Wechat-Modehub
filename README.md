# Wechat-Modehub

微信文章模板库。AI 复现 + 人工审批后收录。

## 用途

- 存储经过审批的微信文章 HTML 模板
- 通过 `catalog.json` 索引快速检索
- 供公众号发布器、排版工具等调用

## 目录结构

```
modehub/
├── catalog.json          # 模板索引
└── templates/
    ├── {id}.html         # 模板 HTML（inline CSS，微信安全）
    └── {id}.json         # 模板元数据
```

## catalog.json 格式

```json
{
  "version": "1.0",
  "templates": [
    {
      "id": "102358",
      "title": "校园社团招新",
      "author": "...",
      "category": "校园",
      "path": "modehub/templates/102358.html",
      "added_at": "2026-05-11"
    }
  ]
}
```

## 收录流程

1. AI 复现原始模板 → `replica.html`
2. 人工审批（对比原稿 + 复现稿）
3. 审批通过后自动推送到本仓库
4. 更新 `catalog.json` 索引
