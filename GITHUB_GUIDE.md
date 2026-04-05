# GitHub 推送指南

## 仓库位置
- **本地仓库**: `F:\github\personal-knowledge-system`
- **知识库工作区**: `F:\Personalknowledgesystem`（日常使用）

---

## 推送到 GitHub 的步骤

### Step 1: 在 GitHub 网站创建仓库

1. 打开浏览器，访问 https://github.com/new
2. 填写信息：
   - **Repository name**: `personal-knowledge-system`
   - **Description**: `基于 AI 的个人知识管理与学习系统`
   - **可见性**: Public（公开）或 Private（私有）
   - **不要勾选** "Add a README file"、"Add .gitignore"、"Choose a license"
3. 点击 **Create repository**

### Step 2: 在本地添加远程仓库

创建成功后，GitHub 会显示推送命令。你也可以直接运行：

```powershell
cd F:\github\personal-knowledge-system

# 添加远程仓库（替换 YOUR_USERNAME 为你的 GitHub 用户名）
git remote add origin https://github.com/YOUR_USERNAME/personal-knowledge-system.git

# 重命名分支为 main
git branch -M main

# 推送到 GitHub
git push -u origin main
```

### Step 3: 输入凭据

推送时会要求输入 GitHub 凭据：
- **用户名**: 你的 GitHub 用户名
- **密码**: 使用 Personal Access Token（不是密码）
  - 创建 Token: https://github.com/settings/tokens
  - 需要勾选 `repo` 权限

---

## 使用 SSH 方式（推荐）

如果你配置了 SSH 密钥：

```powershell
cd F:\github\personal-knowledge-system

# 使用 SSH 地址
git remote add origin git@github.com:YOUR_USERNAME/personal-knowledge-system.git
git branch -M main
git push -u origin main
```

---

## 日常更新流程

当你修改了知识库内容，需要同步到 GitHub：

```powershell
cd F:\github\personal-knowledge-system

# 1. 查看变更
git status

# 2. 添加变更文件
git add .

# 3. 提交
git commit -m "📝 更新知识卡片"

# 4. 推送
git push
```

---

## 注意事项

### 知识库工作区 vs Git 仓库

- **`F:\Personalknowledgesystem`**: 日常学习使用的知识库
- **`F:\github\personal-knowledge-system`**: 用于推送到 GitHub 的副本

当你需要更新 GitHub 仓库时：

```powershell
# 同步更新
Copy-Item -Path "F:\Personalknowledgesystem\knowledge\*" -Destination "F:\github\personal-knowledge-system\knowledge\" -Recurse -Force

cd F:\github\personal-knowledge-system
git add .
git commit -m "📝 同步知识库更新"
git push
```

### .gitignore 规则

当前配置会忽略：
- `knowledge/books/*.md` - 个人书籍笔记
- `knowledge/concepts/*.md` - 个人概念卡片
- 等个人知识卡片文件

保留：
- `knowledge/*/index.md` - 索引文件
- `MEMORY.md` - 全局索引
- `templates/` - 模板文件
- `AIdocs/` - 方案文档

---

## 安装 GitHub CLI（可选）

如果想用命令行创建仓库：

```powershell
# 安装
winget install GitHub.cli

# 登录
gh auth login

# 创建并推送
cd F:\github\personal-knowledge-system
gh repo create personal-knowledge-system --public --source=. --push
```
