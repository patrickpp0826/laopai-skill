# Prompt Template

## 组装约束

- 英文正向提示词用于生图，中文模板用于核对。
- 默认把 6 条风格锚点全部置于最前，占完整正向提示词约 35%–50%，不得少于前 1/3。
- 方括号部分全部替换；没有内容时删除整段，不保留空占位符。
- 固定风格层不得混入主体、服装、道具、地点或动作。
- 每次明确 `{motif_mode}`：默认 `auto`，可选 `none` 或 `sparse`；不得在固定风格层列出具体纹样类型。

## English template

```text
[style anchors]. [subject]. [scene]. [composition/lighting]. [texture/finish]. Motif mode: [motif_mode]. Aspect ratio [aspect_ratio]. Must include: [must_include]. Avoid in content: [must_avoid].
```

展开版：

```text
Use warm off-white paper #F4F0E7 as an active unpainted surface; keep 35–45% of the full frame bare, including irregular gaps inside the subject, and build every colored area from only 2–3 transparent wash passes. Draw with pressure-varying 1–2 px dark-brown or blue-gray lines; leave 40–55% of outer contours open, repeat focal edges with 2–4 strokes offset by 1–4 px, and let at least one stroke overshoot each major junction by 3–8% of that edge length. Build the focal silhouette from 3–5 near-black #0B1118 or deep-indigo #152C3C masses covering 25–40% of the subject; break every mass with one paper-white gap and one opaque white dry-brush scuff, and use only one hard-edged shadow level. Show actual wet watercolor behavior in at least three separated zones: a dark pigment-pooling rim, one cauliflower backrun, one feathered wet edge, and visible granulation; do not imitate watercolor with uniform digital noise or an all-over paper filter. Use no more than five principal colors: warm paper white, near-black, deep indigo, muted blue-gray, and one accent selected from [accent color]; keep the accent below 8% of the frame and place it in 3–6 unequal clusters. Confine dense marks to 15–20% of recognition nodes and reduce every secondary form to one broken wash plus no more than three structural strokes. Decorative fragments are optional: use none by default, or at most 1–2 partial marks derived from shapes already present in the current subject or scene; crop, erase, or wash-obscure 40–80% of each mark, and never introduce a recurring symbol vocabulary. [subject]. [scene and mood]. [composition and lighting]. Tactile low-contrast paper fiber on bare and pale areas only, localized pigment accidents, and an unpolished scanned-paper finish. Motif mode: [motif_mode]. Aspect ratio [aspect_ratio]. Must include: [must_include]. Avoid in content: [must_avoid].
```

## 中文模板

```text
[风格锚点]。[主体]。[场景]。[构图／光线]。[肌理／成图质感]。装饰痕迹模式：[motif_mode]。画幅比例为 [aspect_ratio]。必须包含：[must_include]。内容上避免：[must_avoid]。
```

展开版：

```text
把 #F4F0E7 暖纸白当作未上色的有效画面；全图保留 35%–45% 裸纸，包含进入主体内部的不规则缺口，每块颜色只允许叠加 2–3 遍透明水色。使用带压感变化的 1–2 px 深褐或蓝灰线；40%–55% 外轮廓保持开放，焦点边缘用 2–4 根相距 1–4 px 的线回找，每个主要连接处至少有一根线越界其边长的 3%–8%。用 3–5 块近黑或深靛蓝锁定主体，覆盖主体面积 25%–40%；每个墨块必须同时被一个纸白缺口和一道不透明白色干笔擦痕切开，硬边阴影只有一级。至少在三个分离区域呈现深色积边、回流花、羽化湿边与颗粒沉降，禁止用均匀数字噪点或全画纸纹滤镜冒充水彩。全图主要颜色不超过五种：暖纸白、近黑、深靛蓝、低饱和蓝灰和一种[点缀色]；点缀色低于画面 8%，分成 3–6 个大小不等的色簇。密集笔迹只占识别节点的 15%–20%，每个次要形体简化为一块断裂水色和最多三根结构线。装饰痕迹默认不加；确有构图需要时，最多加入 1–2 个从当前主体或场景既有形状派生的局部痕迹，每个被裁切、擦除或水色遮住 40%–80%，不得形成跨作品反复出现的符号词库。[主体]。[场景与情绪]。[构图与光线]。纸纤维只在裸纸与浅洗处保持低对比可见，并保留局部水色事故和未经抛光的扫描纸面质感。装饰痕迹模式：[motif_mode]。画幅比例为 [aspect_ratio]。必须包含：[must_include]。内容上避免：[must_avoid]。
```

## Negative prompt template

```text
[exclusive_negatives], [applicable universal_negatives], [must_avoid]
```

## 示例 1：人物肖像

### English positive prompt

```text
Use 35–45% bare warm paper #F4F0E7 and only 2–3 transparent wash passes. Use pressure-varying 1–2 px dark-brown or blue-gray lines; leave 40–55% of contours open, repeat focal edges with 2–4 strokes offset by 1–4 px, and overshoot major junctions. Build 25–40% of the subject from 3–5 broken near-black or deep-indigo masses, each cut by paper gaps and white dry-brush scuffs; use one hard shadow level. Show pigment-pooling rims, a cauliflower backrun, a feathered wet edge, and granulation in separate zones. Use paper white, near-black, deep indigo, muted blue-gray, and vermilion only; keep vermilion below 8% in unequal clusters. Confine dense marks to 15–20% of recognition nodes and reduce secondary forms to one broken wash and no more than three structural strokes. A close portrait of a middle-aged woman with short silver hair and a calm direct gaze. Head-and-shoulders framing slightly left of center, broad bare paper on the right, paper reserve lighting the face. Motif mode: none; add no independent decorative fragments. Must include one small red earring. Avoid hats, weapons, crowds, text, and uniform digital texture. Aspect ratio 4:5.
```

### 中文核对稿

```text
保留 35%–45% 裸露暖纸，只叠加 2–3 遍透明水色。使用带压感变化的 1–2 px 深褐或蓝灰线，40%–55% 轮廓开放，焦点边缘由 2–4 根相距 1–4 px 的线回找，主要连接处保留越界线。用 3–5 块断裂近黑或深靛蓝墨块覆盖主体 25%–40%，每块由纸白缺口和白色干笔擦痕切开；硬阴影只有一级。在不同区域分别出现积色边、回流花、羽化湿边和颗粒沉降。全图只用纸白、近黑、深靛蓝、低饱和蓝灰和朱红，朱红低于 8%。密集笔迹只占识别节点 15%–20%，次要形体只用一块断裂水色和最多三根结构线。近景描绘一位银色短发、平静直视的中年女性，头肩构图略偏左，右侧保留大块裸纸。装饰痕迹模式为 none，不添加独立装饰残片。必须包含一枚小红耳环；避免帽子、武器、人群、文字与均匀数字肌理。画幅 4:5。
```

## 示例 2：生活场景

### English positive prompt

```text
Use 35–45% bare warm paper #F4F0E7 and only 2–3 transparent wash passes. Use pressure-varying 1–2 px dark-brown or blue-gray lines; leave 40–55% of contours open, repeat focal edges with 2–4 strokes offset by 1–4 px, and overshoot major junctions. Build 25–40% of the subjects from 3–5 broken near-black or deep-indigo masses, each cut by paper gaps and white dry-brush scuffs; use one hard shadow level. Show pigment-pooling rims, a cauliflower backrun, a feathered wet edge, and granulation in separate zones. Use paper white, near-black, deep indigo, muted blue-gray, and orange-red only; keep orange-red below 8% in unequal clusters. Confine dense marks to faces, hands, fruit, and the teapot; reduce secondary forms to one broken wash and no more than three structural strokes. Two friends prepare breakfast at a small counter, one slicing fruit and the other pouring tea. Medium-wide side view, figures in the left two-thirds, open window and broad bare paper on the right. Motif mode: auto; omit decorative fragments unless one partial mark derived from the steam or counter edge materially improves the negative-space rhythm, and obscure at least half of it with wash. Must include steam and a bowl of oranges. Avoid signage, extra people, text, and uniform digital texture. Aspect ratio 3:2.
```

### 中文核对稿

```text
保留 35%–45% 裸露暖纸，只叠加 2–3 遍透明水色。使用带压感变化的 1–2 px 深褐或蓝灰线，40%–55% 轮廓开放，焦点边缘由 2–4 根相距 1–4 px 的线回找，主要连接处保留越界线。用 3–5 块断裂近黑或深靛蓝墨块覆盖主体 25%–40%，每块由纸白缺口和白色干笔擦痕切开；硬阴影只有一级。在不同区域分别出现积色边、回流花、羽化湿边和颗粒沉降。全图只用纸白、近黑、深靛蓝、低饱和蓝灰和橙红，橙红低于 8%。密集笔迹只放在脸、手、水果和茶壶；次要形体只用一块断裂水色和最多三根结构线。两位朋友在小台面准备早餐，一人切水果，另一人倒茶。中景侧视，人物位于左侧三分之二，右侧敞窗与裸纸留白。装饰痕迹模式为 auto；除非从蒸汽或台面边缘派生的一处局部痕迹能明显改善负空间节奏，否则省略，并让水色遮住它至少一半。必须包含蒸汽和一碗橙子；避免招牌、多余人物、文字与均匀数字肌理。画幅 3:2。
```

## 示例 3：产品／静物

### English positive prompt

```text
Use 35–45% bare warm paper #F4F0E7 and only 2–3 transparent wash passes. Use pressure-varying 1–2 px dark-brown or blue-gray lines; leave 40–55% of contours open, repeat the rim, crown, and strap edges with 2–4 strokes offset by 1–4 px, and overshoot major junctions. Build 25–40% of the watch from 3–5 broken near-black or deep-indigo masses, each cut by paper gaps and white dry-brush scuffs; use one hard shadow level. Show a pigment-pooling rim, a cauliflower backrun, a feathered wet edge, and granulation in separate zones. Use paper white, near-black, deep indigo, muted blue-gray, and vermilion only; keep vermilion below 8% in unequal clusters. Confine dense marks to the dial, crown, hands, and strap joint; reduce other forms to one broken wash and no more than three structural strokes. A compact mechanical wristwatch beside its detached leather strap, three-quarter top view, slightly below center, broad bare paper above. Motif mode: sparse; use one partial mark derived from the dial-and-strap geometry, crop it at the frame edge, and obscure 60–80% with wash; introduce no unrelated ornament. Must include a readable round dial and one loose strap loop. Avoid brand marks, text, packaging, hands, glossy reflections, and uniform digital texture. Aspect ratio 1:1.
```

### 中文核对稿

```text
保留 35%–45% 裸露暖纸，只叠加 2–3 遍透明水色。使用带压感变化的 1–2 px 深褐或蓝灰线，40%–55% 轮廓开放，表圈、表冠和表带边缘由 2–4 根相距 1–4 px 的线回找，连接处保留越界线。用 3–5 块断裂近黑或深靛蓝墨块覆盖腕表 25%–40%，每块由纸白缺口和白色干笔擦痕切开；硬阴影只有一级。在不同区域分别出现积色边、回流花、羽化湿边和颗粒沉降。全图只用纸白、近黑、深靛蓝、低饱和蓝灰和朱红，朱红低于 8%。密集笔迹只放在表盘、表冠、指针和表带连接处；其他形体只用一块断裂水色和最多三根结构线。机械腕表与拆下的皮表带并置，四分之三俯视，主体略低于中心，上方保留裸纸。装饰痕迹模式为 sparse；只使用一个从表盘与表带几何关系派生的局部痕迹，在画框边缘截断，并被水色遮住 60%–80%，不加入无关装饰。必须包含清楚圆形表盘和一个松开的表带环；避免品牌、文字、包装、人手、油亮反射与均匀数字肌理。画幅 1:1。
```
