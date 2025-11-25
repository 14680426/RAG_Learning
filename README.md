# RAG (Retrieval-Augmented Generation) 检索增强生成系统

本项目是一个完整的RAG系统教程，涵盖了从基础概念到高级技术的全面内容。通过Jupyter Notebook的形式，逐步讲解如何构建和优化一个高效的检索增强生成系统。本项目使用的所有模型都是本地化部署的，在3090上可以运行。

## 项目教程

- [RAG实战教程博客](https://blog.csdn.net/weixin_44919384/article/details/154775920?spm=1001.2014.3001.5501)
- [Agent实战教程博客](https://blog.csdn.net/weixin_44919384/article/details/154985538?spm=1001.2014.3001.5501)

## 项目概述

RAG（检索增强生成）是一种结合了信息检索和语言生成的技术，它允许大型语言模型在生成响应时参考外部知识源。这种方法解决了传统语言模型的一些关键限制，如知识截止日期、事实准确性等问题。

## 教程内容

### 01 - 本地问答系统 (Local QA System)
介绍RAG系统的基础构建模块：
- 文档加载和解析
- 文本分割技术
- 向量嵌入模型的使用
- 向量数据库（Chroma）的配置和使用
- 构建基本的问答系统流程

### 02 - 查询优化 (Query Optimization)
深入探讨查询优化技术，提高检索准确性：
- 多查询技术（Multi-query）
- 查询转换和重写
- 上下文压缩检索
- 自查询检索器

### 03 - 路由与查询构建 (Routing and Query Construction)
学习如何智能地路由查询和构建复杂的检索条件：
- 多数据源路由
- 查询构建技术
- 结构化查询处理
- 条件过滤和元数据检索

### 04 - 高级索引与检索策略 (Advanced Indexing and Retrieval Strategies)
掌握高级的文档索引和检索策略：
- 智能分块技术
- 父文档检索器
- 压缩检索器
- 时间加权检索器

### 05 - 重排序与查询集成 (Re-ranking and Query Integration)
深入了解如何优化检索结果的质量：
- 交叉编码器重排序
- 倒数排序融合（RRF）
- 多查询检索集成
- 混合检索技术

### 06 - Embedding微调 (Embedding Fine-tuning)
学习如何针对特定领域数据微调Embedding模型以提升检索效果：
- 下载并转换BCE嵌入模型为Sentence Transformers格式
- 使用本地Qwen模型生成领域特定的问答对
- 微调BCE嵌入模型以适应特定领域
- 评估微调前后模型性能差异

## 项目结构

```
RAG/
├── 01_LocalQASystem.ipynb                 # 基础问答系统教程
├── 02_Query_Optimization.ipynb           # 查询优化技术
├── 03_Routing_and_Query_Construction.ipynb  # 路由和查询构建
├── 04_Advanced_Indexing_and_Retrieval_Strategies.ipynb  # 高级索引和检索策略
├── 05_Re-ranking_and_Query_Integration.ipynb  # 重排序和查询集成
├── 06_Embedding_Finetune.ipynb            # Embedding微调教程
├── Dataset/                              # 数据集目录
│   └── PDF/                              # PDF文档集合
├── Models/                               # 模型文件目录
│   ├── maidalun/                         # 主要嵌入模型
│   ├── model_outdir/                     # 微调后的模型输出目录
│   └── ms-marco-MiniLM-L-6-v2/          # 重排序模型
└── chroma_db/                            # Chroma向量数据库
```

## 核心技术组件

### 文档处理
- 支持多种文档格式（PDF、网页等）
- 智能文本分割算法
- 文档元数据管理

### 向量嵌入
- 使用先进的嵌入模型（如bce-embedding-base_v1）
- 支持自定义嵌入模型
- 本地模型缓存机制
- 支持模型微调以适应特定领域

### 向量数据库
- Chroma向量数据库
- 持久化存储支持
- 高效的相似性搜索

### 检索策略
- 多种检索算法实现
- 查询优化技术
- 结果重排序机制

### 语言模型集成
- 支持主流大语言模型
- 灵活的模型配置
- 本地和云端模型支持

## 使用方法

1. 确保已安装所需的依赖包：
   ```
   pip install langchain langchain-openai chromadb
   ```

2. 运行各教程笔记本，逐步学习RAG系统构建：
   - 从 [01_LocalQASystem.ipynb](01_LocalQASystem.ipynb) 开始了解基础概念
   - 按顺序学习各个高级主题
   - 在 [06_Embedding_Finetune.ipynb](06_Embedding_Finetune.ipynb) 中学习如何微调Embedding模型