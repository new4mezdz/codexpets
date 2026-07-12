# Xiaoxue Codex Pet

一个 Codex 桌面宠物包，形象是 AI 辅助生成的原创 Q 版校园少女“小雪”：白发蓝眸，身穿海军风校服。

> 非官方项目。这个仓库不隶属于、未获授权、未被 OpenAI 赞助或背书；仓库不包含 Codex 官方宠物贴图、Logo、UI 或其他应用资源。

![小雪待机动画预览](xiaoxue/preview.gif)

## 使用

克隆或下载仓库后，把 `xiaoxue` 里的宠物清单和图集复制到 Codex 自定义宠物目录：

```powershell
mkdir "$env:USERPROFILE\.codex\pets\xiaoxue" -Force
copy xiaoxue\pet.json "$env:USERPROFILE\.codex\pets\xiaoxue\pet.json"
copy xiaoxue\spritesheet.webp "$env:USERPROFILE\.codex\pets\xiaoxue\spritesheet.webp"
```

如果你修改过 `CODEX_HOME`，请改用对应目录；也可以从 Codex 的宠物设置中直接打开自定义宠物文件夹。

然后刷新宠物列表并选择 `小雪`，或在 `config.toml` 的 `[desktop]` 下设置：

```toml
selected-avatar-id = "custom:xiaoxue"
```

如果仍显示旧图集，重启一次 Codex 以清除缓存。

## 仓库结构

```text
xiaoxue/
  pet.json              Codex 宠物 manifest
  spritesheet.webp      最终 v2 动态图集
  preview.gif           长待机动画预览
  checksums.sha256      发布文件 SHA-256 校验值
output/pdf/
  xiaoxue-state-preview.pdf  11 行状态与长待机预览
```

## 状态

这个宠物使用 Codex 桌面宠物的 v2 11 行图集约定：

1. `idle` — 长周期随机感待机
2. `running-right` — 向右贴墙慢挪
3. `running-left` — 向左贴墙慢挪
4. `waving` — 挥手
5. `jumping` — 鼠标悬停时害羞
6. `failed` — 失败或受阻
7. `waiting` — 等待输入
8. `running` — 思考、抬头并出现问号
9. `review` — 完成并等待查看
10. `look-000-to-157.5` — 前 8 个鼠标注视方向
11. `look-180-to-337.5` — 后 8 个鼠标注视方向

完整逐页预览：[查看 / 下载状态预览 PDF](output/pdf/xiaoxue-state-preview.pdf)。PDF 包含 11 行状态总览、基础状态帧、64.15 秒待机时间线，以及 16 方向鼠标注视素材。

待机不是短动画机械重复，而是一条预先编排的 64.15 秒时间线：共 72 帧，穿插单眨眼、双眨眼、左右轻瞄、害羞小动作、短挥手和整理衣襟。当前宠物清单不支持运行时随机抽取动作，因此它属于“长周期随机感”，约 64.15 秒后循环。

## 校验

最终发布文件已通过逐帧和浏览器背景播放检查：

- `1536x2288`
- `RGBA`
- `192x208` cells
- Sprite v2，11 行状态
- 72 帧无损动态 WebP
- 64.15 秒无限循环
- 图集约 4.53 MB
- 非待机状态在全部动态帧中保持一致
- 无可见残影、裁切或尺寸跳变

发布文件的 SHA-256 值见 [`xiaoxue/checksums.sha256`](xiaoxue/checksums.sha256)。

## 制作与改造

小雪以静态 v2 图集为基础，再把不规则待机时间线编码进无损动态 WebP。为避免 Codex 自带的待机列计时与 WebP 时间轴互相串帧，每个 WebP 时间点的待机格都保持同一姿势，其余 10 行则逐帧保持不变。

如果你要改造它，建议保留这些约束：

- 单格尺寸固定为 `192x208`
- v2 图集固定为 `8` 列、`11` 行
- `pet.json` 中保持 `spriteVersionNumber: 2`
- 文件名保持为 `pet.json` 与 `spritesheet.webp`
- 修改后重新检查透明边缘、脚底基线和各状态切换

## 许可证和权利说明

见 [LICENSE.md](LICENSE.md)。目前尚未选择开放许可证；公开仓库不自动代表授权再发布、改编或商业使用。
