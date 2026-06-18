# 个人财务 PWA — 部署指南

## 你需要准备什么

- GitHub 账号（已有）
- 10 分钟

---

## 第一步：建两个 GitHub 仓库

### 1-A 公开仓库（放代码）

1. 打开 https://github.com/new
2. Repository name 填：`finance-app`
3. 选 **Public**（必须公开，GitHub Pages 才能免费用）
4. 勾选 **Add a README file**
5. 点 **Create repository**

### 1-B 私有仓库（放你的数据）

1. 再次打开 https://github.com/new
2. Repository name 填：`my-finance-data`
3. 选 **Private**（必须私有，保护你的数据）
4. 勾选 **Add a README file**
5. 点 **Create repository**

---

## 第二步：上传 App 文件到公开仓库

1. 打开 `finance-app` 仓库
2. 点 **Add file → Upload files**
3. 把以下文件全部拖入：
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
4. 滚到底部点 **Commit changes**

---

## 第三步：开启 GitHub Pages

1. 在 `finance-app` 仓库点顶部 **Settings**
2. 左侧菜单找 **Pages**
3. Source 选 **Deploy from a branch**
4. Branch 选 **main**，文件夹选 **/ (root)**
5. 点 **Save**
6. 等约 1 分钟，页面会显示你的网址：
   `https://你的用户名.github.io/finance-app`

---

## 第四步：生成 Personal Access Token

> Token 是你的"数据库密钥"，只存在你手机本地，不会上传任何地方。

1. 打开 https://github.com/settings/tokens/new
2. Note 填：`finance-app`
3. Expiration 选 **No expiration**（或者选你喜欢的有效期）
4. 勾选权限（只需要这一个）：
   - **repo** → 勾选最顶层的 `repo`（会自动全选子项）
5. 滚到底部点 **Generate token**
6. **立刻复制这个 token**（页面离开后就看不到了）
   格式类似：`ghp_xxxxxxxxxxxxxxxxxxxx`

---

## 第五步：在手机上打开并配置

1. 用手机 Safari 打开：`https://你的用户名.github.io/finance-app`
2. 首次打开会看到设置界面，填入：
   - **GitHub Token**：刚才复制的 `ghp_xxx...`
   - **GitHub 用户名**：你的 GitHub 用户名
   - **数据仓库名**：`my-finance-data`
3. 点 **开始使用**

---

## 第六步：添加到 iPhone 主屏幕

1. Safari 打开 App 后，点底部**分享按钮**（方框+箭头图标）
2. 滑动找到 **添加到主屏幕**
3. 名称改为 **财务**，点**添加**
4. 桌面会出现 App 图标，点开是全屏体验

---

## 日常使用

- **录入**：打开 App → 录入 tab → 填金额类别 → 保存（自动同步到 GitHub）
- **查看**：消费/存款/Buffer 等 tab 实时计算
- **跨设备**：电脑浏览器也可以打开同一个网址，数据一致

---

## 数据安全说明

| 内容 | 存放位置 | 谁能看到 |
|------|---------|---------|
| App 代码 | 公开仓库 | 任何人（只有代码，没有数据）|
| 你的交易记录 | 私有仓库 | 只有你 |
| GitHub Token | 你的手机本地 | 只有你 |
| 账单/预算/存款 | 私有仓库 | 只有你 |

---

## 常见问题

**Q：同步失败怎么办？**
A：检查 Token 是否有 `repo` 权限，以及私有仓库名是否拼写正确。

**Q：Token 过期了怎么办？**
A：重新生成一个新 Token，在 App 设置页（长按标题）重新填入。

**Q：想从 Google Sheet 导入历史数据怎么办？**
A：从 Google Sheet 导出 CSV，告诉我，我帮你写一个导入脚本。

**Q：忘记了自己的 GitHub 用户名？**
A：登录 GitHub 后右上角头像旁边就是。
