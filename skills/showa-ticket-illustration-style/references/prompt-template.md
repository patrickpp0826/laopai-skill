# 昭和票券插画 · 提示词模板与纠偏

## 完整票券模式

```text
{fixed_style_layer}. Depict {subject} in an original small narrative scene. {orientation} ticket composition: the illustration occupies roughly 55 percent, a clean title and small-information area occupies roughly 30 percent, and a newly drawn simplified curved-line emblem occupies a small reserved area. {palette}. Use only the supplied copy: {copy}; if no copy is supplied, leave the text areas blank for later typesetting. {must_include}. Aspect ratio {aspect_ratio}.
```

若用户只要票券气质、不需要真实票据，号码章可换成纯装饰性抽象纹样，不加入序列号、兑奖说明或真实发行机构。

## 纯插画模式

```text
{fixed_style_layer}. Create a standalone illustration of {subject}, with playful cut-paper silhouettes, restrained overprinting texture and generous warm-paper gaps. No ticket numbers or institutional text. {palette}. {must_include}. Aspect ratio {aspect_ratio}.
```

## 纠偏

| 结果偏差 | 调整 |
| --- | --- |
| 看起来像普通现代扁平插画 | 增加局部网点、油墨颗粒、轻微套色偏移，以及标题栏与纸白的节奏。 |
| 看起来像真正邮票 | 删除齿孔、邮戳和航空邮边条；恢复票券的插画区与信息区。 |
| 做旧过重 | 减少全图褐色滤镜、裂纹与污点；保留清楚的原色块和局部旧纸感。 |
| 信息太多 | 缩减到一个标题、少量小字和一个小纹章；增大插画。 |
| 与参考票券太像 | 更换主体、画面关系、色彩主次和纹章形状；删除参考图中的机构名、金额与编号。 |
| 文字乱码 | 生成无字底图并预留排字区；真实文字在后期添加。 |
