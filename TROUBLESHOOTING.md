# SSH 连接问题排查

## 当前状态

SSH 连接测试失败，可能的原因：

1. **网络问题**（防火墙、代理、VPN）
2. **公钥未正确添加到 GitHub**
3. **GitHub SSH 服务暂时不可用**

## 解决方案

### 方案 1: 验证公钥是否正确添加

1. **查看你的公钥**：
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

2. **在 GitHub 上验证**：
   - 访问：https://github.com/settings/keys
   - 确认你的公钥已存在
   - 确认公钥内容完全匹配

3. **删除并重新添加**（如果需要）：
   - 在 GitHub 上删除旧的 SSH key
   - 重新添加：`cat ~/.ssh/id_ed25519.pub` 的输出

### 方案 2: 使用 HTTPS + Personal Access Token（临时方案）

如果 SSH 持续有问题，可以临时使用 HTTPS：

```bash
cd /Users/mingyangxia/focus/llms
git remote set-url origin https://github.com/MingyangXiaKira/llm-notes.git
git push -u origin main
```

需要 Personal Access Token（不是密码）：
- 创建：https://github.com/settings/tokens
- 权限：勾选 `repo`

### 方案 3: 检查网络和防火墙

```bash
# 测试 GitHub SSH 端口
nc -zv github.com 22

# 如果失败，可能需要配置代理或检查防火墙
```

### 方案 4: 使用 GitHub CLI（如果已安装）

```bash
gh auth login
gh repo create llm-notes --public --source=. --remote=origin --push
```

## 快速验证命令

```bash
# 查看远程仓库配置
git remote -v

# 查看待推送的提交
git log origin/main..HEAD --oneline 2>/dev/null || git log --oneline -5

# 测试 SSH 连接
ssh -T git@github.com -v
```

## 推荐操作

1. **先验证公钥**：确认 GitHub 上的公钥和本地完全一致
2. **如果 SSH 还是不行**：临时使用 HTTPS + Token
3. **稍后再试 SSH**：可能是临时的网络问题

