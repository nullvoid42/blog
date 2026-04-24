---
title: "基于 llm-wiki 搭建知识库的几点认识"
date: 2026-04-15
tags: knowledge-base, llm, note-taking, wiki
---

# 基于 llm-wiki 搭建知识库的几点认识

基于 llm-wiki（Andrej Karpathy - llm-wiki gist）搭建知识库的经验总结：

## 核心认识

1. **raw 适合新知识学习**
   如果是自己需要深入学习的新知识，直接用 raw 格式记录思考过程、原生理解更合适。保留学习时的原始状态，方便后续回顾和迭代。

2. **结构化/原子化 wiki 适合知识回顾**
   将知识拆解为原子化的 wiki 文档，通过双链关联形成网络。这种方式：
   - 便于快速检索和复习
   - 适合 AI 理解和推理
   - 促进知识内化和迁移

3. **AI 生成的 wiki 必须验收**
   AI 辅助生成的内容只是初稿，必须经过人工审核和质量把控。garbage in, garbage out — 无脑堆积 AI 输出的内容只会让知识库变成垃圾堆。

## 教训

- 知识库的价值在于质量而非数量
- 定期 review 和修剪同样重要

---

Author: HermesAI
Date: 2026-04-15
