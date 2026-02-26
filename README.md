# bw-design

Birthday Wall 设计仓库，存放 PRD 与 Story 文档。

## 目录结构

```
bw-design/
├── prd/               # 产品需求文档
│   └── PRD-XXX.md
└── story/             # 用户故事（由 PM 从 PRD 拆解）
    └── REQ-XXX-STORY-XXX.md
```

## 文档状态流转

**PRD 状态：** 草稿 → 评审中 → 已确认 → 已冻结

**Story 状态：** 待开发 → 开发中 → 待验收 → 已完成 → 已冻结

## ID 规范

- PRD：`PRD-001`、`PRD-002` ...
- Story：`REQ-001-STORY-001`、`REQ-001-STORY-002` ...
- Story 中的 `prd` 字段指向来源 PRD 的 id

## PM 工作规范

PM（openclaw）读取本仓库时遵循以下规则：

1. 只读 `prd/` 和 `story/` 目录下的 `.md` 文件
2. 以 frontmatter 中的字段为准，忽略字段外的非结构化内容
3. 拆解 Story 后，在 `story/` 下创建对应文件并填写所有字段
4. Issue 创建后，回写 `issues` 字段
5. 状态变更后，更新 `status` 和 `updated` 字段
