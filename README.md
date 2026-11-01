# Minecraft 图片改绘 Skill

将照片、合影、建筑、物体或地点改绘为 Minecraft 风格。默认保留原片比例、构图、人物关系与明暗分布，采用接近原版的方块构件、玩家比例和像素材质。

这是一个以中文编写的非官方 Skill。它提供提示词与改绘规则，实际生图由宿主中的图片工具完成。

## 直接使用通用提示词

将 [prompts/general-photo.txt](prompts/general-photo.txt) 全文与照片一起交给支持图片编辑的模型，可以追加尺寸、指定文字或改造要求。

提示词可独立使用。由 Skill 为具体图片编写提示词时，会删掉不适用的要求，再补充本图需要保留的内容。

## 作为 Skill 使用

将本仓库放入宿主支持的技能目录，保留根目录的 [SKILL.md](SKILL.md) 与相邻文件。在 Codex 的默认技能目录中，可用：

```sh
git clone https://github.com/d4yt1m3/minecraft-style-image-prompt.git ~/.codex/skills/minecraft-style-image-prompt
```

目标目录已有同名 Skill 时，请按现有安装方式更新，避免覆盖本地修改。

附图后可以这样请求：

```text
使用 $minecraft-style-image-prompt，将这张照片整体改绘为 Minecraft 风格，保留原比例，生成一张。
```

也可以只要提示词，或指定不同的造型与照明：

- “保留合影的人数和顺序，采用接近原版的玩家比例。”
- “保留原片夜景的光源和暗部，使用光影表现。”
- “允许自由方块改编，增加自定义附件，保持简单游戏光照。”

## 造型与光照

两项分别选择，改变照明不自动改变人物比例或模型复杂度。

| 项目 | 默认 | 可按用户要求选择 |
| --- | --- | --- |
| 造型 | 接近原版的方块构件与玩家比例 | 自由方块改编，允许更多自定义模型与比例 |
| 光照 | 简单游戏光照 | 光影表现，允许柔和投影、泛光或反射 |

这些是创作选项，不是官方游戏模式。保留照片的光照关系，指保留光源位置、颜色和亮暗范围；具体照明表现按所选风格重新处理。

指定文字和来源中清楚且重要的字样按原文保留。无法辨认的内容可以降低细节或省略，不能补写另一句可读文字。准确文案仍需在成图后核对。

## 文件

| 文件 | 内容 |
| --- | --- |
| [SKILL.md](SKILL.md) | 任务选择、保留优先级、提示词编写与成图检查 |
| [prompts/general-photo.txt](prompts/general-photo.txt) | 可独立使用的通用照片提示词 |
| [references/visual-style.md](references/visual-style.md) | 方块造型、人物器物、光照、文字和参考选择 |
| [agents/openai.yaml](agents/openai.yaml) | Skill 显示名称与默认调用提示 |

生成式改绘可能改变面部、小字或结构细节；图片不等于可游玩的地图或原版搭建蓝图。

## 来源与许可

本项目沿用 [titanfall2-style-image-prompt](https://github.com/d4yt1m3/titanfall2-style-image-prompt) 中形成的照片改绘方法，并间接参考 [xiaoTN/zelda-style-image-prompt](https://github.com/xiaoTN/zelda-style-image-prompt) 的提示词组织方式。详见 [来源说明](NOTICE.md)。

本项目采用 [MIT License](LICENSE)，保留上游 xiaotn 的版权声明，并为新增与修改内容保留 d4yt1m3 的署名。

仓库不包含用户照片、生成样图或游戏图片。Minecraft 及相关商标属于各自权利人；本项目与 Mojang、Microsoft 无隶属或背书关系。外链资料不包含在本仓库许可中。
