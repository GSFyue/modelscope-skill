# 图片重绘提示词｜参考模板与词库

本文件是 `SKILL.md` 的补充资料，包含三个模型的完整模板、锚点示例、目标词库和风格改变写法。主流程以 `SKILL.md` 为准。

## 1｜Midjourney 模板

### 默认模板

> faithful redraw of the reference image, keep the original composition, camera angle, subject placement, scale relationship and overall style unchanged, preserve the original character / scene design, improve image quality, clarity, material detail, structural stability and lighting consistency, cleaner edges, refined textures, better detail separation, [核心锚点 3—6 个], keep original visual style, no redesign, no extra elements, high fidelity, refined rendering --ar X:X --style raw

填写要求：

- 核心锚点用逗号分隔的短英文短语，例如 `left-side facial close-up, right-side full-body front view, white traditional outfit, giant pale-yellow sphere, gray-blue plain background`。
- 默认只保留 `--ar` 与 `--style raw`，不要堆入复杂参数。
- 用户把原图作为图片参考、且需要更强一致性时，按实际需要增加 `--iw`。
- 画幅比例未知时询问用户，或沿用原图比例，不要编造。

## 2｜Seedream 模板

> **重绘指令：** 严格参考原图重绘，保持原图构图、镜头视角、主体位置、大小比例和整体风格不变；保持原角色或场景核心设计，不重新设计，不增加多余元素。
>
> **优化目标：** 提升整体画质、清晰度、材质细节、结构稳定性和光影统一性，使画面更干净、更精致，同时保持原图视觉效果。
>
> **主体锚点：** [3—6 个核心锚点]
>
> **风格质量：** 保持原风格，[4—8 个必要质量词]。

## 3｜Image 2.5 模板

> 根据参考图进行高一致度重绘。保持原图构图、视角、主体位置、比例关系、角色或场景设计和原始风格不变，不重新设计，不添加多余元素。在忠实保留原画面的前提下，提升整体画质、清晰度、材质细节、结构稳定性和光影统一性。核心锚点：[3—6 个核心锚点]。整体效果更干净、更细腻、更稳定，并保持原图的视觉方向。

## 4｜主体锚点示例

### 角色设定图

- 左侧面部大特写
- 中间正面服装全身展示
- 右侧完整背面
- 黑长发兽耳女性
- 深蓝黑幻想长裙
- 灰蓝纯色影棚背景

### 巨物场景

- 巨型淡黄色球体
- 左下极小人物
- 顶部浓密垂藤
- 静水倒影
- 极简黄绿色调

## 5｜优化目标词库

按图片实际问题选择，不要全部堆入。

### 清晰度

- higher clarity
- cleaner details
- refined edges
- better fine detail
- reduced blur

中文对应：提升整体清晰度、清理细节、优化边缘、改善微细节、减少糊感。

### 材质

- improved material definition
- realistic fabric texture
- refined hair strands
- better fur detail
- clearer metal texture
- more natural skin texture

中文对应：提升材质精度、优化布料纹理、优化发丝、优化毛发、增强金属质感、改善皮肤质感。

### 光影

- more coherent lighting
- smoother highlight transition
- cleaner shadow structure
- better light separation
- natural light falloff

中文对应：优化光影连续性、提升高光与阴影过渡、清理阴影结构、增强光线分离、自然的明暗衰减。

### 稳定性

- improved anatomical consistency
- cleaner structure
- better shape definition
- reduced visual artifacts
- consistent proportions

中文对应：改善结构稳定性、提升形体准确度、减少生成瑕疵、保持比例一致。

### 完成度

- refined rendering
- higher fidelity
- polished finish
- cleaner image
- better visual coherence

中文对应：提升渲染完成度、提高保真度、优化整体完成度、画面更干净、视觉更统一。

## 6｜风格改变模式

仅当用户明确要求更写实、真人化、CG 化、动漫化、水墨化、电影化、更梦幻、更怪异或更科幻时启用。

提示词结构：

> 保持项 → 指定修改项 → 优化目标 → 主体锚点 → 新风格质量词

示例：

**保持项：** 保持原图构图、镜头视角、人物位置、比例关系与画面结构不变。

**指定修改项：** 将整体视觉语言改为电影感写实风格，保留原角色辨识点与服装结构。

**优化目标：** 提升材质真实度、光影层次、皮肤与布料质感，保持画面统一。

**主体锚点：** 左侧人物半身特写；右侧全身站姿；深色长风衣；雨后街道背景。

**新风格质量词：** cinematic realism, natural skin texture, soft directional light, film grain, muted color grading, high fidelity。

不得把「改风格」误解为「重新设计画面」。

## 7｜常见问题处理

### 用户只说「重绘」

按默认模式执行：原构图、原主体、原比例、原风格不变，只提升画质与完成度。

### 用户只说「优化一下」

按 Level 1 处理，不主动改变风格，不增加或删除元素。

### 用户要求「更清晰」

重点写清晰度、边缘、微细节与材质精度，不借机重构画面。

### 用户要求「换风格」但没说换成什么

只追问一次目标风格；若用户不指定，按 Level 2 原风格增强处理。

### 参考图结构复杂

允许适度增加锚点与描述，但仍以 3—6 条锚点为优先；不要演变成完整画面复述。

### 用户要求「完全照搬」

说明会保持构图、主体与风格方向，但生成模型不会逐像素复制；不要承诺像素级一致。

## 8｜扩展自检

- [ ] 是否明确写了「保持原图」。
- [ ] 是否明确写了优化目标。
- [ ] 是否默认保持原风格。
- [ ] 是否避免重新设计。
- [ ] 是否保留构图和主体比例。
- [ ] 主体锚点是否只有 3—6 条。
- [ ] 是否删除了无用细节。
- [ ] 是否没有把图片重新完整描述一遍。
- [ ] 是否没有堆砌大量质量词。
- [ ] Midjourney 是否足够短且高密度。
- [ ] Seedream 是否以执行指令为主。
- [ ] Image 2.5 是否自然、直接、简洁。
- [ ] 三个版本是否表达同一个重绘目标。

## 9｜核心原则

> 重绘提示词不是「描述原图」，而是「控制原图不要跑偏，并明确告诉模型该优化什么」。

执行顺序永远是：

> 保持项 → 优化项 → 核心锚点 → 风格质量。

默认行为：

> 原图构图不变 + 原主体不变 + 原风格不变 + 提升画质与完成度。

最终追求：

> 更短、更准、更容易执行，而不是更长、更完整。

本参考对应「图片重绘提示词 V0.2 精简高效重绘版」。
