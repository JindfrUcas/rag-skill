# RAG Skill

这是一个基于 RAG（检索增强生成）技术的 AI Skill，允许用户上传文档并基于文档内容进行智能问答。

## 接口定义

### 1. 上传并处理文档
将文档内容发送至向量数据库进行索引。

- **路径**: `/ingest`
- **方法**: `POST`
- **参数**:
  - `content`: (string, required) 需要被索引的文本内容。
  - `metadata`: (object, optional) 文档元数据。

### 2. 文档问答检索
基于已上传的文档内容回答问题。

- **路径**: `/query`
- **方法**: `POST`
- **参数**:
  - `query`: (string, required) 用户的提问。
  - `topK`: (number, optional) 检索的相似片段数量，默认为 3。

## 运行环境配置

- **Runtime**: Node.js
- **Port**: 3000
- **Env**:
  - `OPENAI_API_KEY`: 必填，用于 Embedding 和生成回答。
