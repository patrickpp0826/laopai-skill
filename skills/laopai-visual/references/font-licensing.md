# 字体授权与替代规则

本文件是生成工作流的字体白名单，不构成法律意见。许可证以字体上游仓库随具体版本附带的原文为准；下载或分发字体文件时必须同时保留相应许可证。

## 默认白名单

| 用途 | 首选字体 | 已核验许可 | 使用说明 |
| --- | --- | --- | --- |
| 香港字形黑体、正文、标签 | Chiron Hei HK / 昭源黑体 | SIL OFL 1.1 | 可用于商业与非商业成品；不得单独售卖字体文件，修改与再分发须遵守 OFL。 |
| 香港字形宋体、编辑标题 | Chiron Sung HK / 昭源宋体 | SIL OFL 1.1 | 同上。 |
| 亲和圆体、餐饮与生活标签 | Chiron GoRound TC / 昭源环方 | SIL OFL 1.1 | 同上；不要把圆体当成儿童化装饰。 |
| 香港字形通用替代 | Noto Sans CJK HK / Noto Serif CJK HK | SIL OFL 1.1 | 适合跨平台排版与字形覆盖。 |
| 泛中日韩通用替代 | Source Han Sans / Source Han Serif | SIL OFL 1.1 | 使用 HK 字形版本；留意许可证中的 Reserved Font Name 条款。 |
| 英文窄体、数字、票据编号 | Roboto Condensed | Google Fonts 开源许可 | 只从 Google Fonts 或官方上游下载，并随版本核对许可证。 |

官方核验入口：

- Chiron Hei HK: https://github.com/chiron-fonts/chiron-hei-hk/blob/release/LICENSE.md
- Chiron Sung HK: https://github.com/chiron-fonts/chiron-sung-hk/blob/release/LICENSE.md
- Chiron GoRound TC: https://github.com/chiron-fonts/chiron-go-round-tc
- Noto CJK: https://github.com/notofonts/noto-cjk
- Source Han Sans: https://github.com/adobe-fonts/source-han-sans
- Source Han Serif: https://github.com/adobe-fonts/source-han-serif
- Google Fonts: https://developers.google.com/fonts

## 不自动放行

- 截图、招牌、海报或 Logo 中无法准确识别的字体。
- 标注“免费”“个人免费”但没有可追溯许可证原文的字体。
- 仅从字体下载站、网盘、素材包或二次转载处取得的字体。
- 商业字库、品牌定制字、电影标题字、书法家手写字及其描摹版本。
- 授权只覆盖个人用途、试用、非商业或指定平台的字体。

## 生成与交付规则

1. 先描述字形特征，再从白名单选择字体：例如“高对比宋体”映射到 Chiron Sung HK，“紧凑无衬线”映射到 Chiron Hei HK，“亲和圆角”映射到 Chiron GoRound TC。
2. 不因为视觉相似就宣称是同一字体，也不根据截图判断可商用。
3. 图像模型不能稳定渲染指定字体时，生成少字版本或无字底图，并明确给出后期字体建议。
4. 用户指定白名单外字体时，要求其提供官方授权链接或许可证文件；无法核验则改用白名单替代项并说明替换。
5. 输出前区分三种权利：字体许可证、参考图版权、品牌商标。字体可商用不等于图像、Logo 或品牌元素可复用。
