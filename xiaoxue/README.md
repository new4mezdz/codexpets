# Xiaoxue / 小雪

Xiaoxue is an unofficial custom pet for the Codex desktop app.

小雪是为 Codex 桌面应用制作的非官方自定义宠物。

![Random-like idle preview](preview.gif)

## Features / 特点

- White hair, blue eyes, and a navy-style school uniform.
- A 64.15-second, 72-frame random-like idle timeline with blinks, glances, shy fidgets, a short wave, and a ribbon adjustment.
- Shy pointer-hover reaction.
- Slow wall-hugging shuffle while the pet is moved.
- Looks upward and shows a question mark while thinking.
- 16-direction pointer gaze on supported Codex versions.
- Sprite v2, 1536 × 2288, lossless animated WebP.

---

- 白发、蓝眸与海军风校服。
- 64.15 秒、72 帧的随机感待机时间线，包含眨眼、轻瞄、害羞小动作、短挥手和整理衣襟。
- 鼠标悬停时会害羞。
- 移动宠物时会贴着边缘慢慢挪动。
- 思考时抬头并出现问号。
- 在受支持的 Codex 版本中提供 16 方向鼠标注视。
- Sprite v2，1536 × 2288，无损动态 WebP。

## Install / 安装

1. Download the complete `xiaoxue` folder.
2. In Codex, open the custom pet folder from the Pets settings panel.
3. Copy the `xiaoxue` folder into that directory without renaming its files.
4. Refresh the pet list and select **小雪**. Restart Codex once if the old spritesheet is still cached.

---

1. 下载完整的 `xiaoxue` 文件夹。
2. 在 Codex 的宠物设置面板中打开“自定义宠物文件夹”。
3. 将 `xiaoxue` 文件夹复制进去，不要修改内部文件名。
4. 刷新宠物列表并选择 **小雪**。如果仍显示旧图集，请重启一次 Codex。

## Compatibility / 兼容性

Tested on Codex for Windows `26.707.3748.0`. The long idle sequence is a pre-baked random-like timeline because the current custom-pet manifest does not expose runtime-random animation selection. It repeats after approximately 64.15 seconds.

已在 Windows 版 Codex `26.707.3748.0` 上测试。由于当前自定义宠物清单不支持运行时随机选择动画，长待机采用预先编排的随机感时间线，大约每 64.15 秒循环一次。

## Files / 文件

- `pet.json` — pet metadata / 宠物信息
- `spritesheet.webp` — installable sprite atlas / 可安装图集
- `preview.gif` — idle preview / 待机预览
- `checksums.sha256` — SHA-256 checksums / 文件校验值

## License / 许可证

No license has been selected yet. The artwork and accompanying files remain under the owner's default copyright until a license is added.

目前尚未指定许可证。在后续添加许可证之前，形象与配套文件保留作者的默认著作权。
