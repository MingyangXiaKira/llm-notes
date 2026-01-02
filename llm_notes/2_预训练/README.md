# 预训练 (Pre-training)

## 核心内容 (Core Topics)

### 1. 预训练目标
- Masked Language Modeling (MLM)
- Causal Language Modeling (CLM)
- Next Sentence Prediction (NSP)
- Span Corruption

### 2. 数据处理
- Tokenization (BPE, WordPiece, SentencePiece)
- Data preprocessing pipelines
- Dataset construction
- Data quality and filtering

### 3. 训练策略
- Distributed training
- Mixed precision training
- Gradient accumulation
- Learning rate scheduling
- Optimizer selection (Adam, AdamW)

### 4. 训练技巧
- Warmup strategies
- Dropout and regularization
- Gradient clipping
- Checkpointing

## 代码示例 (Code Examples)

See `code/` folder for:
- Pre-training scripts
- Data preprocessing pipelines
- Training loop implementations
- Distributed training setup

## 问题与讨论 (Questions and Discussions)

See `questions/` folder for:
- Pre-training objectives comparison
- Training optimization techniques
- Data pipeline design
- Scaling challenges

