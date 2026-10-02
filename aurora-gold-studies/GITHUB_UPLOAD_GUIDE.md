# GitHub 上传与在线访问指南（Studies 1–3）

本指南教你把这个合并项目（含 `Study1`、`Study2`、`Study3` 三个文件夹）上传到 GitHub，并启用 **GitHub Pages**，让三个研究的实验网页都能在线上通过链接直接打开。

---

## 1. 准备工作

1. 注册一个 GitHub 账号：[github.com](https://github.com/signup)（已有账号可跳过）。
2. 记住你的**用户名**（username），后面访问网址要用。
3. 本项目的本地位置：

```
C:\Users\fangt\Doubao\chats\2026-10-02\new-chat\aurora-gold-studies
```

里面已经有：
- `index.html`（根主页，能跳转到三个研究的入口页）
- `README.md`（项目总览，会显示在 GitHub 首页）
- `GITHUB_UPLOAD_GUIDE.md`（就是本文件）
- `Study1\`、`Study2\`、`Study3\`（三个研究的全部网页）

> 目录名、文件名**保持原样**即可。网页之间用的是**相对路径**，只要按原结构上传，链接就不会断。

---

## 2. 创建仓库（Repository）

1. 登录 GitHub，点右上角 **+** → **New repository**。
2. 填写：
   - **Repository name**（仓库名）：例如 `aurora-gold-studies`
   - **Public / Private**：建议选 **Public**（GitHub Pages 免费托管公开仓库；私有仓库的 Pages 需付费，且访客无法访问）。
3. **不要勾选** “Add a README file”（我们已有 README，避免冲突）。
4. 点 **Create repository**。

---

## 3. 上传文件（任选一种方式）

### 方式 A：网页直接上传（最简单，无需安装软件）

1. 进入刚创建的仓库页面，点 **Add file** → **Upload files**。
2. 在文件资源管理器中打开 `aurora-gold-studies` 文件夹，**全选里面的内容**（`index.html`、`README.md`、`GITHUB_UPLOAD_GUIDE.md`、`Study1`、`Study2`、`Study3` 文件夹），拖入上传框。
3. 下方填写提交说明，例如 `Initial upload of Studies 1–3`。
4. 点 **Commit changes**。

### 方式 B：用 GitHub Desktop（适合之后经常更新）

1. 下载安装 [GitHub Desktop](https://desktop.github.com/) 并登录。
2. 点 **File → Add local repository**，选择 `aurora-gold-studies` 文件夹。
3. 点击 **Publish repository**，输入仓库名，点 **Publish**。

### 方式 C：命令行 git（适合熟悉命令行）

```bash
cd "C:\Users\fangt\Doubao\chats\2026-10-02\new-chat\aurora-gold-studies"
git init
git add .
git commit -m "Initial upload of Studies 1-3"
git branch -M main
git remote add origin https://github.com/<你的用户名>/aurora-gold-studies.git
git push -u origin main
```

---

## 4. 启用 GitHub Pages（在线访问网页的关键）

1. 打开你的仓库页面，进入 **Settings**（设置）。
2. 左侧菜单点 **Pages**。
3. 在 **Branch** 处选择 `main`，文件夹选 `/ (root)`，点 **Save**。
4. 稍等 1–2 分钟，页面顶部会出现：

```
Your site is live at https://<你的用户名>.github.io/aurora-gold-studies/
```

---

## 5. 在线访问各个网页

启用后，根主页会自动显示 `index.html`，并链接到三个研究：

| 页面 | 网址 |
|---|---|
| 根主页（三研究入口） | `https://<用户名>.github.io/aurora-gold-studies/` |
| Study 1 场景索引 | `.../Study1/index.html` |
| Study 2 场景索引 | `.../Study2/index.html` |
| Study 3 会话选择 | `.../Study3/index.html` |

把 `<用户名>` 换成你的 GitHub 用户名即可。示例：

```
https://zhangsan.github.io/aurora-gold-studies/Study1/index.html
```

### 如何在问卷里接入这些网页

- **Credamo（Study 1、Study 2）**：在问卷中插入链接时，指向对应条件页，并追加 `return` 参数跳回问卷：

  ```
  https://<用户名>.github.io/aurora-gold-studies/Study1/paid_monetary.html?return=<你的问卷URL>
  ```

- **Prolific（Study 3）**：把链接指向会话页，并带上 Prolific 参数：

  ```
  https://<用户名>.github.io/aurora-gold-studies/Study3/study3_provider_paid_monetary.html?PROLIFIC_PID={{%PROLIFIC_PID%}}&STUDY_ID={{%STUDY_ID%}}&SESSION_ID={{%SESSION_ID%}}&return=<你的问卷URL>
  ```

  （`{{%...%}}` 为 Prolific 的占位符，平台会自动替换成真实值。）

> 也可以直接把问卷链接指向**根主页**或各研究的 `index.html`，页面会把 URL 里的参数自动透传到具体场景页。

---

## 6. 验证与常见问题

**验证：**
- 用手机或隐私窗口打开上面的网址，确认三张卡片都能点进去、场景页能正常显示。
- 点击场景页的 `Continue`，确认能跳回问卷（若配了 `return`）。

**常见问题：**
- **打开是 404**：检查是否已在 Settings → Pages 里启用并选择了 `main` + `/ (root)`；上传后可能需要等几分钟。
- **网页样式乱了 / 链接打不开**：多半是文件名或文件夹名的大小写与链接不一致。相对路径区分大小写，保持一致即可。
- **更新内容后没变化**：GitHub Pages 有缓存，刷新或等待几分钟即可；也可在 Settings → Pages 里手动触发重新部署。
- **页面无法访问（403）**：仓库是 Private 且未付费开通 Pages，改为 Public 即可。
- **`return` 参数里的 `&` 报错**：在问卷后台填链接时，`&` 需要写成 `&amp;`（HTML 转义）。

---

## 7. 之后更新

改完本地文件后，用方式 B（GitHub Desktop）或方式 C（命令行 `git add . && git commit -m "..." && git push`）重新推送，GitHub Pages 会自动更新，无需重新上传。
