# ModelScope Skill：图片重绘提示词

这是一个可直接导入魔搭（ModelScope）Skills 中心的技能包，遵循 Agent Skills 的 `SKILL.md` 规范。

## 技能内容

`skills/image-redraw-prompt/`

- `SKILL.md`：技能入口，说明适用场景、执行流程、输出结构与自检规则。
- `reference.md`：Midjourney、Seedream、Image 2.5 的完整模板，锚点示例与优化词库。

## 功能

把 1 张参考图转换为可直接用于生成模型的高保真重绘提示词，默认输出三个版本：

1. Midjourney
2. Seedream
3. Image 2.5

默认行为是保持原图构图、视角、主体位置、比例、角色或场景设计与原风格不变，只提升清晰度、材质、光影、结构稳定性与整体完成度。

也支持：

- 局部修改重绘，例如只改服装颜色。
- 原风格增强。
- 明确指定后的风格重构，例如真人化、CG 化、动漫化。

## 在 ModelScope 发布

1. 将本仓库设为公开仓库。
2. 打开 <https://modelscope.cn/skills/create>。
3. 填入本仓库的 GitHub 地址，选择 `image-redraw-prompt` 并确认创建。
4. 发布完成后复制技能详情页地址，回填到比赛提测页的「作品链接」。

## 使用

把 `skills/image-redraw-prompt` 目录放到 Agent 的技能目录，或在支持 Skills 的工具中导入该目录即可。技能不依赖外部 API，也不需要额外配置。

版本：V0.2 精简高效重绘版。
