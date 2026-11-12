# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

书签管理应用 — 通过 Web 界面进行书签的增删改查和搜索。

## 技术栈

| 层       | 技术                              |
| -------- | --------------------------------- |
| 前端框架 | Next.js App Router               |
| 语言     | TypeScript                        |
| 样式     | Tailwind CSS                      |
| 后端     | Next.js API Routes                |
| 数据库   | Prisma + SQLite                   |
| 部署     | Vercel                            |

## 项目结构

```
src/
├── app/              # Next.js 页面路由
│   ├── api/          # API 路由（统一返回 { success, data?, error? }）
│   ├── layout.tsx    # 全局布局
│   └── page.tsx      # 首页
├── components/       # React 组件
│   ├── ui/           # 通用 UI 组件
│   └── features/     # 业务组件
├── lib/              # 工具函数、配置
├── prisma/           # Schema、迁移、种子数据
└── types/            # TypeScript 类型定义
```

## 编码规范

- **组件**：函数式组件 + React Hooks，文件名 PascalCase
- **工具代码**：camelCase 命名
- **API 响应**：统一 `{ success: boolean, data?: any, error?: string }`
- **数据库**：所有操作通过 Prisma Client，禁止 raw SQL 直连

## Git 约定

- `.env`、`prisma/dev.db` 写入 `.gitignore`，不提交到仓库
- 新功能在独立分支开发，完成后再合并到主分支
