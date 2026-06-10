# GitHub Pages 部署指南

## 方式一：通过 GitHub Web 界面（推荐，最简单）

### 步骤 1：创建仓库
1. 打开 https://github.com/new
2. Repository name 填写：`loop-engineering-guide`
3. 选择 **Public**（GitHub Pages 免费版需要公开仓库）
4. 勾选 **Add a README file**
5. 点击 **Create repository**

### 步骤 2：上传文件
1. 在新仓库页面，点击 **Add file** → **Upload files**
2. 把 `index.html` 文件拖入上传区域
3. 点击 **Commit changes**

### 步骤 3：启用 GitHub Pages
1. 进入仓库的 **Settings** 标签
2. 左侧菜单点击 **Pages**
3. **Source** 选择 **Deploy from a branch**
4. **Branch** 选择 **main** / **master**，文件夹选 **/(root)**
5. 点击 **Save**
6. 等待 1-2 分钟，刷新页面，会看到提示：
   > Your site is live at `https://你的用户名.github.io/loop-engineering-guide/`

---

## 方式二：通过 Git 命令行

```bash
# 1. 进入项目目录
cd loop-engineering-guide

# 2. 初始化 Git 仓库
git init

# 3. 添加文件
git add index.html README.md

# 4. 提交
git commit -m "Initial commit: Loop Engineering Guide"

# 5. 添加远程仓库（替换为你的用户名）
git remote add origin https://github.com/你的用户名/loop-engineering-guide.git

# 6. 推送
git branch -M main
git push -u origin main

# 7. 然后到 GitHub 仓库 Settings → Pages 启用（见方式一的步骤 3）
```

---

## 方式三：使用 GitHub Desktop（图形化）

1. 下载 [GitHub Desktop](https://desktop.github.com/)
2. File → Add local repository → 选择 `loop-engineering-guide` 文件夹
3. 填写 summary，点击 **Commit to main**
4. 点击 **Publish repository** → 确认仓库名 → **Publish**
5. 然后到 GitHub 网页启用 Pages（见方式一的步骤 3）

---

## 🎨 自定义域名（可选）

如果你想用自己的域名（如 `loop.yourdomain.com`）：

1. 在仓库根目录创建 `CNAME` 文件，内容写你的域名：
   ```
   loop.yourdomain.com
   ```
2. 在你的域名 DNS 设置中添加 CNAME 记录：
   - 主机记录：`loop`
   - 记录值：`你的用户名.github.io`
3. 等待 DNS 生效（通常几分钟到几小时）

---

## ✅ 部署后检查清单

- [ ] 访问 `https://你的用户名.github.io/loop-engineering-guide/` 能正常打开
- [ ] 导航栏能正常跳转
- [ ] 可点击展开的知识点正常工作
- [ ] 流程图能点击并显示详情
- [ ] 代码块的"复制"按钮正常工作
- [ ] 手机端访问布局正常

---

## 🆘 常见问题

**Q: 页面打开是 404？**
A: GitHub Pages 部署需要 1-2 分钟。如果超过 5 分钟还是 404，检查 Settings → Pages 中的分支设置是否正确。

**Q: 样式没有加载？**
A: 确保 `index.html` 中的 CSS 是内联的（当前版本已经是内联样式，不需要外部文件）。

**Q: 想更新内容怎么办？**
A: 修改 `index.html` 后重新上传到仓库，GitHub Pages 会自动重新部署（约 1-2 分钟）。
