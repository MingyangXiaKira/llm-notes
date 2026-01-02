# Git 和 GitHub 设置说明

## 当前状态

✅ **本地 Git 仓库已创建并提交**
- 所有文件已提交到本地仓库
- 提交记录保存在本地（`.git` 文件夹）
- 当前有 1 个提交

❌ **尚未连接到 GitHub**
- 本地仓库和 GitHub 是独立的
- 你的代码只在本地，没有备份到云端

## 本地 Git vs GitHub

### 本地 Git（你现在有的）
```
你的电脑
├── llm_interview_prep/  (你的文件)
└── .git/                (Git 历史记录，本地保存)
```

### GitHub（云端仓库）
```
GitHub 服务器
└── 你的仓库 (备份和分享)
```

## 如何连接到 GitHub

### 方法 1: 在 GitHub 上创建新仓库后连接

1. **在 GitHub 上创建新仓库**
   - 访问 https://github.com/new
   - 仓库名：例如 `llm-interview-prep`
   - 不要初始化 README（因为本地已有文件）

2. **连接本地仓库到 GitHub**
   ```bash
   cd /Users/mingyangxia/focus/llms
   git remote add origin https://github.com/你的用户名/llm-interview-prep.git
   git branch -M main  # 可选：将分支名改为 main
   git push -u origin main
   ```

### 方法 2: 使用 SSH（更安全）

1. **检查是否有 SSH 密钥**
   ```bash
   ls -la ~/.ssh
   ```

2. **如果没有，生成 SSH 密钥**
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```

3. **添加 SSH 密钥到 GitHub**
   - 复制公钥：`cat ~/.ssh/id_ed25519.pub`
   - 在 GitHub Settings → SSH and GPG keys 中添加

4. **使用 SSH URL 连接**
   ```bash
   git remote add origin git@github.com:你的用户名/仓库名.git
   git push -u origin main
   ```

## 常用命令

### 查看状态
```bash
git status              # 查看工作区状态
git log --oneline       # 查看提交历史
git remote -v           # 查看远程仓库配置
```

### 提交变更
```bash
git add .               # 添加所有变更
git commit -m "消息"     # 提交
git push                # 推送到 GitHub（连接后）
```

### 从 GitHub 拉取
```bash
git pull                # 拉取远程更新
```

## 重要提示

⚠️ **当前你的代码只在本地**
- 如果电脑出问题，代码可能丢失
- 建议尽快连接到 GitHub 进行备份

✅ **连接 GitHub 后**
- 代码会自动备份到云端
- 可以在任何地方访问
- 可以与他人协作
- 可以查看在线版本历史

## 需要帮助？

如果你想要我帮你连接到 GitHub，请告诉我：
1. 你的 GitHub 用户名
2. 你想创建的仓库名称
3. 你想使用 HTTPS 还是 SSH

