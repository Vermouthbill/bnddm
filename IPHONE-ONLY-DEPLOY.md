# BND DM Vault Beta 0.1 — iPhone-only 部署说明

> 这份包只包含应用代码和模拟数据，不包含真实 Weverse DM。
> 目标：只用 iPhone Safari + GitHub 网页，把 PWA 放到 HTTPS 地址并添加到主屏幕。

## 你需要准备

- 一个 GitHub 账号
- iPhone Safari
- 本压缩包解压后的 7 个文件

## A. 在 iPhone 上创建 GitHub 仓库

1. Safari 打开 GitHub 并登录。
2. 新建 repository，名称建议：`bnd-dm-vault`。
3. Beta 测试阶段建议只上传本包内的代码和模拟数据，不要把未来导出的聊天备份 JSON、真实录屏、截图或媒体文件提交到仓库。
4. 如果使用 GitHub Free 并希望 GitHub Pages 免费发布，通常使用 public repository 最省事；注意这意味着“应用源代码”公开，但不等于 iPhone 浏览器里的本地数据库公开。

## B. 上传解压后的文件

把以下文件全部放在仓库根目录，不要再套一层文件夹：

- `index.html`
- `sw.js`
- `manifest.webmanifest`
- `icon.svg`
- `.nojekyll`
- `README.txt`
- `IPHONE-ONLY-DEPLOY.md`

在 GitHub 仓库页面使用 **Add file → Upload files**，一次选择这些文件并提交。

如果 iPhone Safari 的文件选择器不方便多选，可以分批上传；最终只要它们都位于仓库根目录即可。

## C. 打开 GitHub Pages

1. 进入仓库 **Settings**。
2. 找到 **Pages**。
3. 在 **Build and deployment**：
   - Source：`Deploy from a branch`
   - Branch：`main`
   - Folder：`/(root)`
4. 保存。
5. 等待 GitHub 显示站点已发布，然后点开它提供的 HTTPS 地址。

GitHub 官方当前文档允许从指定 branch 的根目录发布 Pages。

## D. 在 iPhone 上安装成 PWA

1. 必须使用 **Safari** 打开发布后的 HTTPS 地址。
2. 首次打开后等待页面加载完，刷新一次。
3. 点 Safari 的 **分享** 按钮。
4. 选择 **添加到主屏幕**。
5. 从桌面的 `BND Vault` 图标重新打开。
6. 在应用的 Beta 诊断页检查：
   - HTTPS：应为支持
   - IndexedDB：应为支持
   - Service Worker：应为支持
   - Standalone / 主屏幕运行：从桌面图标打开后应为是

## E. 第一轮只测试模拟数据

建议按这个顺序测试：

1. 导入模拟数据。
2. 切换六名成员。
3. 用日期导航跳转。
4. 搜索韩文或中文模拟文本。
5. 关闭网页再从桌面重新打开，检查数据是否仍在。
6. 导出 JSON 备份。
7. 删除/清空测试数据后，再用 JSON 恢复。
8. 最后再测试一段你自己制作的模拟聊天录屏。

在 Weverse 对真实 DM 的私人离线归档许可明确之前，不要导入真实付费 DM。

## F. 数据到底在哪里？

- GitHub Pages：只托管 HTML / JS / manifest / 图标等“应用代码”。
- 聊天数据库：保存在你当前 iPhone 上、这个网页来源对应的浏览器本地存储中。
- JSON 备份：只有你主动点导出后，才生成一个文件。
- 原录屏：目前仍需你自己保留；Beta 不会把视频本体装进 JSON 备份。

### 非常重要

不要把以下内容上传到 GitHub 仓库：

- 真实 DM 录屏
- 真实 DM 截图
- 真实聊天 JSON 备份
- 下载的艺人媒体
- 任何包含付费私信正文的文件

## G. 更新 Beta 时

以后我给你 Beta 0.2 / 0.3 时，先在旧版里导出 JSON 备份，再替换 GitHub 仓库里的应用代码文件。不要删除浏览器数据，除非新版说明明确要求。

即便数据通常会继续存在，升级前备份仍然是强制建议。

## 出问题时怎么给我信息

在 BND DM Vault 的诊断页导出诊断 JSON，并告诉我：

- 哪一步出问题
- iPhone 系统版本
- 是 Safari 标签页打开还是主屏幕 PWA 打开

诊断文件不应包含真实聊天正文；上传前仍可自己打开确认。
