# 星际突袭 Star Strike

一款使用 **原生 HTML + CSS + JavaScript Canvas** 开发的单文件太空射击网页游戏。零依赖、零构建，双击 `index.html` 即可游玩，同时完美适配电脑与手机。

## 在线演示

GitHub Pages：<https://redemption725.github.io/space-shooter/>

手机浏览器打开后，可通过浏览器菜单「添加到主屏幕」，像 App 一样全屏启动。

## 游戏特性

- 玩家飞船，霓虹科幻画风，三层视差流动星空背景
- 敌机自动持续刷新，子弹圆形碰撞检测，击毁触发爆炸粒子特效
- 实时分数统计与本地最高分持久化（刷新页面不丢失）
- 玩家护甲血条，被撞击 / 中弹扣血，受伤短暂无敌，避免连续掉血
- 分数达标自动进入下一关，敌机速度与刷新频率随关卡提升
- 每 3 关出现大型 BOSS：多段血量，发射环形 + 朝玩家扇形弹幕，击败即通关
- 完整的开始 / 暂停 / 结束界面，「再来一局」无需刷新页面
- 切到后台自动暂停；边界 clamp 防卡屏；dt 上限防穿墙

## 操作方式

| 平台 | 移动 | 射击 | 暂停 |
| --- | --- | --- | --- |
| 电脑 | 方向键 或 W A S D | 空格 | P / Esc |
| 手机 | 屏幕左侧十字方向键 | 右下角发射按钮 | 切后台自动暂停 |

## 本地运行

无需安装任何环境，直接用浏览器打开 `index.html` 即可：

```text
双击 index.html
```

## 部署到线上

### 方案一：GitHub Pages（长期免费）

1. 在 GitHub 新建一个 **Public** 仓库（如 `space-shooter`）
2. 上传 `index.html` 并提交
3. 仓库 **Settings → Pages**，Source 选择 `main` 分支、根目录，保存
4. 约 1 分钟后得到 `https://<用户名>.github.io/space-shooter/`

使用 GitHub CLI 一键发布并开启 Pages：

```bash
git init
git add index.html
git commit -m "Add Star Strike"
git branch -M main
gh repo create space-shooter --public --source=. --remote=origin --push
gh api -X POST /repos/<用户名>/space-shooter/pages -f "source[branch]=main" -f "source[path]=/"
```

### 方案二：Netlify Drop（最快）

打开 <https://app.netlify.com/drop>，将 `index.html` 拖入页面，几秒后即可获得公开链接。

## 技术栈

- HTML5 / CSS3
- 原生 JavaScript（无框架、无打包工具）
- Canvas 2D API
- localStorage

## 目录结构

```text
space-shooter/
├── index.html   # 游戏全部代码（HTML + CSS + JS）
├── LICENSE      # MIT 开源协议
└── README.md    # 项目说明
```

## License

[MIT](./LICENSE)
