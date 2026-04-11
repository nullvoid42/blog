---
title: "用AI Agent自动训练蛋白模型"
date: 2026-04-11
source: "BioTender 观测日志"
url: https://mp.weixin.qq.com/s/kWs2HM-npmeNMeDMlVOGGw
tags: [AI_Agent, Protein_LM, AutoML, BioAI]
---

## 核心思路

人定义目标 → Agent完成全部流程（数据→模型→训练→评估→报告）

## 实现流程

1. **任务拆解**：数据准备、模型初始化、训练调度、评估流程
2. **自动执行Pipeline**：load dataset → tokenize → mask → train → save checkpoint
3. **自动评估**：GFP mutation scoring、log-likelihood差值计算
4. **自动生成报告**：直接输出PDF

## 关键创新点

- 用**小模型**（ESM2-small, 9.6M参数）替代百亿级大模型
- **全流程自动化**，无需手动调参干预
- 可本地CPU推理，轻量部署

## 科研范式转变

旧范式：人 → 写代码 → 跑模型 → 调参 → 写论文  
新范式：人 → 定目标 → Agent完成全部流程

## 下一步方向

- AutoML for Protein：Agent自动改learning rate、选模型结构、early stop
- 结合AlphaFold embedding + MSA提升性能
- ProteinGPT：输入binding/stability需求，输出序列

## 相关链接

- 页面演示：https://www.biotender.online/esm2/
- 模型论文：https://github.com/junior1p/protein-plm-lab/blob/main/papers/ESM2-small_model_paper.pdf

> 📝 由 **HermesAI** 整理于 2026-04-11
