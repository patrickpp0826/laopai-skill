# 迁移测试方案

## 执行规则

每个测试 prompt 都按顺序拼接：

1. 原样粘贴 `style-fingerprint.md` 中完整的 6 条 V2.1 `style_dna_anchors`；
2. 紧接对应的英文内容层；
3. 合并专属负向约束、通用负向约束和该测试的 negative prompt。

不得继续使用旧版 `Mixed-media illustration...` 宽泛前缀，也不得减少“越界回找线、局部湿水色事故”两类核心受控不规则性。五个测试必须覆盖 `none`、`auto`、`sparse` 三种 `{motif_mode}`，装饰痕迹不能成为通过测试的必要条件。

## 通过标准

1. 不靠人物、黑衣、武器、鸟翼或既有构图才能辨认风格。
2. 裸纸占 `35%–45%`，并以缺口进入主体；不是单纯米色背景。
3. `40%–55%` 外轮廓开放，焦点边缘可见 `2–4` 根错位回找线，主要连接处有越界、回钩或未擦净起稿线。
4. 主体由 `3–5` 块蓝黑重块锁定，每块同时有纸白切口和白色干笔擦痕；硬阴影只有一级。
5. 至少三个分离区域分别可见积色暗边、回流花、羽化湿边与颗粒沉降中的三种，且不存在全画均匀纸纹滤镜。
6. 全图不超过五个主色，只用一种跳色；跳色低于 `8%`，分成 `3–6` 个不等色簇。
7. 密集笔迹只占识别节点 `15%–20%`；每个次要形体只有一块断裂水色与最多三根结构线。
8. `{motif_mode: none}` 时装饰痕迹为 0；`auto` 时为 0–1；`sparse` 时为 1–2。若出现，只能从当前测试主体或场景的既有几何派生，并被破坏 `40%–80%`；五张图之间不得重复同一符号组合。
9. 不出现参考图中的角色、服装、道具、动作或版式复刻。

## 1. 一只乌鸦

### English content layer

```text
A single crow stands on a thin bare branch with its head turned slightly toward the viewer. Concentrate recognition detail around the eye, beak, shoulder joint, feet, and tail split; reduce the remaining feathers to two broken indigo masses. Place the bird in the lower-left third with broad bare paper above and to the right. Use cyan as the single accent in three unequal clusters near the eye, branch joint, and one tail gap. Motif mode: none; add no independent decorative fragments. Aspect ratio 4:5.
```

### Negative prompt

```text
uniform thick outlines, closed clean line art, contour-hugging scratches, smooth gradients, uniform digital watercolor texture, identical grain across the frame, evenly spaced splatters, recurring house-style symbols, decorative motif library carried across outputs, repeated motifs, seamless ornament, photorealism, 3D render, glossy feathers, duplicated bird, extra wings, cage, person, text, watermark, signature, logo
```

## 2. 一只茶杯

### English content layer

```text
One ceramic teacup filled with dark tea, with a readable elliptical rim, one handle, one contact shadow, and a thin curl of steam. Place the cup slightly right of center in a three-quarter top view and leave the left half mostly bare. Concentrate detail at the rim overlap, handle joints, tea surface, and contact point; reduce the cup wall to one broken wash. Use vermilion as the single accent in three unequal clusters. Motif mode: auto; omit decorative fragments unless one partial mark derived from the cup rim or steam path improves the left-side negative-space rhythm, and obscure at least 60% of it. Aspect ratio 1:1.
```

### Negative prompt

```text
uniform thick outlines, closed clean line art, smooth product gradients, uniform digital watercolor texture, identical grain across the frame, evenly spaced splatters, recurring house-style symbols, decorative motif library carried across outputs, repeated motifs, seamless ornament, glossy product photography, 3D render, distorted rim, broken handle, duplicated cup, brand mark, text, watermark, signature, packaging, hands
```

## 3. 一位老人

### English content layer

```text
An elderly person with silver hair and deeply lined hands sits upright and looks out of frame, wearing a plain light cardigan. Use a waist-up portrait left of center with both hands visible and broad bare paper on the right. Concentrate detail only at the eyes, nose turn, mouth corners, knuckles, and cardigan opening; reduce sleeves and background to broken washes and fewer than three structural strokes per form. Use vermilion as the single accent in four unequal clusters. Motif mode: none; add no independent decorative fragments. Aspect ratio 4:5.
```

### Negative prompt

```text
uniform thick outlines, closed clean line art, contour-hugging scratches, multi-layer soft facial shading, waxy skin, uniform digital watercolor texture, recurring house-style symbols, decorative motif library carried across outputs, repeated motifs, seamless ornament, photorealism, 3D render, malformed hands, extra fingers, duplicated person, fantasy costume, weapon, crowd, text, watermark, signature, logo
```

## 4. 一片山地湖泊

### English content layer

```text
A high mountain lake enclosed by steep ridges, with a narrow shoreline and one small cluster of distant trees; no people or buildings. Use a slightly elevated wide view, dark ridges entering from the lower-left and upper-right, and broad bare paper across the lake and sky. Concentrate detail at one shoreline bend, the nearest ridge break, and the tree cluster; reduce distant terrain to one wash and three lines per ridge. Use orange-red as the single accent in three unequal mineral-like marks. Motif mode: sparse; use no more than two partial marks derived only from the shoreline bend and nearest ridge break, and erase or wash-obscure 50–80% of each. Aspect ratio 16:9.
```

### Negative prompt

```text
uniform thick outlines, closed clean line art, mirror-smooth reflection, airbrushed sky gradient, uniform digital watercolor texture, recurring house-style symbols, decorative motif library carried across outputs, repeated motifs, seamless ornament, uniformly detailed terrain, photorealism, 3D render, matte painting, duplicated mountains, people, buildings, boats, text, watermark, signature, logo
```

## 5. 抽象概念“喜悦”

### English content layer

```text
Express joy without figures, faces, lettering, or recognizable objects: several compressed dark forms below center open into rising arcs and unequal separated clusters toward the upper right. Keep at least 45% bare paper between the released forms. Concentrate dense marks at three expansion nodes only; reduce every other form to one wash and two overshooting lines. Use vermilion as the single accent in five unequal clusters. Motif mode: auto; use zero decorative fragments unless one partial mark derived from an existing expansion arc clarifies the release direction, and obscure 60–80% of it. Aspect ratio 4:5.
```

### Negative prompt

```text
uniform thick outlines, closed clean geometry, smooth vector arcs, airbrushed gradients, uniform digital watercolor texture, evenly spaced splatters, recurring house-style symbols, decorative motif library carried across outputs, repeated motifs, seamless ornament, uniformly dense composition, logo design, photorealism, 3D render, literal smiling face, emoji, recognizable object, text, watermark, signature
```

## 发现内容复制时改哪一句

优先收紧 `style-fingerprint.md` 的 `do_not_copy_from_refs`，不要削弱描述画法的 `style_dna_anchors`。若复制的是站位、镜头或画面分区，在内容层追加：

```text
Derive a new composition solely from the current content variables; do not preserve the reference layout, pose geometry, camera angle, negative-space map, color-block placement, or subject scale relationships.
```
