# 如何推送到 GitHub

## 当前状态

✅ 远程仓库已配置：`https://github.com/MingyangXiaKira/llm-notes.git`
✅ 本地代码已提交
❌ 需要认证才能推送

## 方法 1: 使用 Personal Access Token (推荐)

### 步骤：

1. **创建 Personal Access Token**
   - 访问：https://github.com/settings/tokens
   - 点击 "Generate new token" → "Generate new token (classic)"
   - 名称：例如 "llm-notes-push"
   - 权限：勾选 `repo` (完整仓库权限)
   - 点击 "Generate token"
   - **重要**：复制生成的 token（只显示一次！）

2. **使用 Token 推送**
   ```bash
   cd /Users/mingyangxia/focus/llms
   git push -u origin main
   ```
   - Username: `MingyangXiaKira`
   - Password: **粘贴你的 Personal Access Token**（不是 GitHub 密码）

3. **或者将 token 保存到 URL（一次性）**
   ```bash
   git remote set-url origin https://MingyangXiaKira:你的TOKEN@github.com/MingyangXiaKira/llm-notes.git
   git push -u origin main
   ```

## 方法 2: 使用 GitHub CLI

如果你安装了 GitHub CLI：

```bash
gh auth login
git push -u origin main
```

## 方法 3: 使用 SSH（更安全，推荐长期使用）

### 生成 SSH 密钥：

```bash
ssh-keygen -t ed25519 -C "141198127+MingyangXiaKira@users.noreply.github.com"
```

### 添加 SSH 密钥到 GitHub：

1. 复制公钥：
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

2. 在 GitHub 添加：
   - 访问：https://github.com/settings/keys
   - 点击 "New SSH key"
   - 粘贴公钥内容
   - 保存

3. 更改远程 URL 为 SSH：
   ```bash
   git remote set-url origin git@github.com:MingyangXiaKira/llm-notes.git
   git push -u origin main
   ```

## 验证推送成功

推送成功后，访问：
https://github.com/MingyangXiaKira/llm-notes

你应该能看到所有文件！

## 快速命令参考

```bash
# 查看远程仓库
git remote -v

# 查看状态
git status

# 推送代码
git push

# 拉取更新
git pull
```

