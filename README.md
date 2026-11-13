# 鸟鸟大作战 · BirdBonk

一款受自动攻击生存游戏启发的独立鸟类游戏。移动躲避敌人、收集经验、选择升级，并在每次冒险发现随机鸟类。WASD / 方向键移动，手机在游戏区域拖动；攻击自动进行。无需账号或后端，图鉴和纪录保存在浏览器本地。

## 运行和部署

使用任意静态服务器提供本目录（例如 `python -m http.server 8000`），访问对应地址。提交到 GitHub 的 `main` 分支后，`.github/workflows/deploy.yml` 通过 GitHub Actions 发布 Pages；仓库 Settings → Pages 的 Source 必须选择 GitHub Actions。静态路径为相对路径，支持项目 Pages 子路径。

鸟类索引和图片按需从 jsDelivr 加载，首次加载需要网络；索引不可用时使用翠鸟作为后备，图片不可用时使用 emoji。游戏本身不需要后端，但这不是完整离线应用。清除浏览器数据会删除本地存档，换设备不会同步。

## 素材和说明

鸟类插画来自 [Bird Album](https://birdalbum.com/) / [huashu-bird-sticker](https://github.com/alchaincyf/huashu-bird-sticker)，遵循 [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)；插画由 AI 生成，可能有识别错误。鸟种索引由上游提供，运行时随机抽取，上游数据和 CDN 可用性会影响覆盖率。玩法代码和界面为独立实现，不包含 PokéBonk 游戏本体、精灵素材或音频。

## 后续路线

1. 验证移动端性能及平衡；添加不同鸟类能力、更多敌人、地图与音效。
2. 固定上游数据版本，压缩与分批缓存贴纸，加入搜索、图鉴分页与离线资源策略。
3. 把游戏状态更新与绘制拆成可复用模块，适配微信小游戏 Canvas、触控及 `wx` 本地存储；需单独开发和审核，网页不能直接成为微信小游戏。
4. 桌面/移动应用可使用 WebView 或桌面容器封装，并按平台要求处理网络资源和存储；如需跨设备存档、排行榜或联机，再设计后端。
