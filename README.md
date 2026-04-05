# 个人知识库系统

> 基于 AI 的个人知识管理与学习系统

## 📖 简介

这是一个基于 OpenClaw 的个人知识库系统，支持：
- 📚 **书籍学习**：6 步学习流程，自动提取概念、思想、场景
- 📝 **文章学习**：快速提取核心观点，生成知识卡片
- 💡 **概念学习**：联网搜索，自动整理定义与示例
- 🔗 **知识关联**：双向链接，构建知识网络

## 🗂️ 目录结构

```
Personalknowledgesystem/
├── AIdocs/                    # 方案文档
│   ├── 个人知识库系统实现方案.md
│   └── 个人知识库系统实现方案_优化版.md
│
├── knowledge/                 # 知识库主目录
│   ├── MEMORY.md              # 全局知识索引
│   ├── domains/               # 知识领域
│   ├── books/                 # 书籍卡片
│   ├── concepts/              # 概念卡片
│   ├── ideas/                 # 核心思想卡片
│   ├── scenarios/             # 应用场景卡片
│   └── problems/              # 解决问题卡片
│
├── templates/                 # 卡片模板
│   ├── book-card.md
│   ├── concept-card.md
│   ├── idea-card.md
│   ├── scenario-card.md
│   └── problem-card.md
│
└── README.md                  # 本文件
```

## 🔧 安装 Skill

将 `skills/knowledge-learner` 复制到你的 OpenClaw skills 目录：

```
复制到: D:\Qclaw-soft\resources\openclaw\config\skills\knowledge-learner\
```

或在 OpenClaw 中运行：

```
安装 skill: knowledge-learner
```

## 🚀 快速开始

### 前置条件

- 安装 [OpenClaw](https://github.com/openclaw/openclaw)
- 配置 LLM API（Claude / GPT / DeepSeek 等）

### 使用方法

在 OpenClaw 中说：

```
帮我学习《思考，快与慢》这本书
```

AI 会自动执行 6 步学习流程：
1. 创建学习记录
2. 搜索作者信息
3. 获取书籍信息
4. 提取知识结构（概念、思想、场景、问题）
5. 建立关联关系
6. 生成学习报告

### 其他命令

```
# 学习文章
帮我学习这篇文章：https://example.com/article

# 学习概念
帮我学习"元认知"这个概念

# 检索知识
我学过哪些关于决策的知识？
```

## 📚 知识卡片类型

| 类型 | 说明 | 示例 |
|------|------|------|
| 📚 书籍 | 书籍学习笔记 | 《思考，快与慢》 |
| 💡 概念 | 知识概念卡片 | 认知偏差、元认知 |
| 💭 思想 | 核心思想卡片 | 系统1与系统2 |
| 🎯 场景 | 应用场景卡片 | 决策优化 |
| 🔧 问题 | 解决问题卡片 | 避免认知陷阱 |

## 🔗 知识关联

使用双向链接 `[[卡片名]]` 建立关联：

```markdown
## 关联概念
- [[认知偏差]]
- [[系统1与系统2]]

## 来源
- [[思考，快与慢]]
```

## 📊 技术架构

```
OpenClaw AI Agent
    │
    ├── 文件读写 → 创建/读取知识卡片
    ├── 联网搜索 → 获取书籍、作者信息
    ├── 记忆系统 → 检索已学知识
    └── knowledge-learner Skill → 学习流程自动化
```

## 📝 开发计划

- [ ] 知识图谱可视化
- [ ] 自动化学习（Heartbeat 定时学习）
- [ ] 导出为 Obsidian 笔记库
- [ ] 导出为 Anki 卡片

## 📄 许可证

MIT License

## 🙏 致谢

- [OpenClaw](https://github.com/openclaw/openclaw) - AI Agent 框架
- 所有知识领域的作者和贡献者
