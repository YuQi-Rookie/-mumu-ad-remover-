# MuMu 模拟器一键去广告工具

> 作者：**玉柒**

一个纯前端网页工具，自动生成 Windows 批处理脚本，一键去除 MuMu 模拟器的所有广告，不影响模拟器正常运行。

## 功能特性

- **Hosts 广告域名屏蔽** — 屏蔽 12+ 广告/统计域名，从网络层阻断广告请求
- **开屏广告去除** — 覆写并锁定 `imageManager.json` + 锁定 `startupImage` 目录，双重保障
- **广告配置禁用** — 在 `config.ini` 中写入 `[AdConfig] enable_ad=0`，从配置层禁用广告
- **弹窗广告服务禁用** — 替换 `MuMuPlayerService.exe` 为空只读文件
- **海外版模式** — 通过 adb 在 `build.prop` 写入 `ro.build.version.overseas=true`，去除主界面轮播 Banner 和「每日新发现」游戏推荐
- **自动版本检测** — 支持 MuMu 12 / 5.x / 6.x 全版本，自动扫描 8+ 安装路径
- **一键还原** — 配套还原脚本，随时恢复到原始状态

## 支持版本

- MuMu 模拟器 12（旧版）
- MuMu 模拟器 5.x / 6.x（新版，含 V6.5.9）

## 本地使用

直接用浏览器打开 `index.html` 即可使用，无需任何后端服务。

## 部署到 GitHub + Cloudflare Pages

### 第一步：上传到 GitHub

1. 登录 [GitHub](https://github.com)，点击右上角 **+** → **New repository**
2. 仓库名称填写 `mumu-ad-remover`，选择 **Public**，点击 **Create repository**
3. 创建后，在仓库页面点击 **uploading an existing file**
4. 将本目录下的 `index.html` 和 `README.md` 拖拽上传，点击 **Commit changes**

### 第二步：通过 Cloudflare Pages 部署

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com)
2. 左侧菜单选择 **Workers & Pages** → **Create** → **Pages** 标签 → **Connect to Git**
3. 选择 GitHub，授权 Cloudflare 访问你的仓库
4. 选择刚才创建的 `mumu-ad-remover` 仓库，点击 **Begin setup**
5. 构建设置保持默认：
   - Framework preset: **None**
   - Build command: 留空
   - Build output directory: `/`（根目录）
6. 点击 **Save and Deploy**
7. 等待约 1 分钟，部署完成后会获得一个 `*.pages.dev` 域名
8. （可选）在 **Custom domains** 中绑定你自己的域名

部署完成后，任何人都可以通过 Cloudflare 提供的域名访问这个工具。

## 项目结构

```
mumu-ad-remover/
├── index.html    # 主页面（单文件，包含所有 CSS/JS）
└── README.md     # 项目说明文档
```

## 免责声明

本工具仅供学习交流使用。脚本内容完全透明，用户可自行审查代码后再决定是否运行。使用本工具产生的一切后果由使用者自行承担。

## 作者

**玉柒**
