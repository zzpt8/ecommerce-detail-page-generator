# Usage Guide

## What this skill does

This skill helps ChatGPT create an industrial-grade ecommerce detail-page generation workflow from product information. It is designed for Chinese ecommerce and image-generation workflows where users need more than a single prompt.

It can output:

- structured product brief
- category and compliance profile
- page-by-page detail-page plan
- mobile ecommerce copy
- unified visual system
- page-level image generation prompts
- layout specification for text overlay
- QC checklist and retry instructions

## Best use cases

Use it for:

- Douyin ecommerce vertical detail pages
- Taobao/Tmall product detail image sets
- Xiaohongshu product selling pages
- Pinduoduo product selling visuals
- AI image-generation prompt packs for ecommerce products
- industrializing a product-detail-page prompt workflow
- auditing whether an existing detail-page prompt is production-ready

## Recommended user input

A strong input includes:

```text
产品名称：
产品类目：
产品简介：
核心卖点：
目标人群：
使用场景：
平台：
比例：9:16
图片数量：8张
风格：
主色调：
是否有原图：
必须出现：
禁止出现：
文案要求：自动生成 / 我提供文案
补充要求：
```

## Minimal input

The skill can run with minimal input such as:

```text
产品：黄芪
平台：抖音电商
比例：竖版
目标人群：30岁以上宝妈
风格：户外背景、暖黄配色、扁平风
文案：自动生成
输出：8张连贯详情页图像提示词
```

When fields are missing, ChatGPT should infer cautiously and mark assumptions.

## Recommended output request

For a complete industrial workflow, ask:

```text
请根据以下产品信息，输出完整工业级电商详情页生成包：Brief、合规边界、页面结构、逐页文案、统一视觉系统、逐页图像提示词、排版规范、质检与失败页重试方案。
```

For only image-generation prompts, ask:

```text
请只输出逐页图像生成提示词和 negative prompt，要求适合后期叠加中文文案。
```

For auditing an existing prompt, ask:

```text
请评估这份详情页提示词是否能用于工业级批量生成，并给出改造方案。
```

## Recommended production workflow

1. Use the skill to generate structured brief and strategy.
2. Review compliance boundaries and copy.
3. Generate image backgrounds page by page.
4. Overlay exact copy using a layout/design engine.
5. Run OCR and visual QC.
6. Retry only failed pages.

## Important limitations

- Do not rely on image models to render large Chinese text accurately.
- Do not generate unsupported claims or fake credentials.
- High-risk categories still need human review before commercial publishing.
- Final platform compliance depends on the seller's qualifications, product category, and current platform rules.


## V2 recommended input additions

For stronger conversion planning, include any of the following when available:

```text
流量来源：搜索 / 短视频 / 直播 / 推荐流 / 小红书种草 / 广告 / 私域
用户阶段：冷启动 / 已有需求 / 正在比价 / 准备下单
客单价：低 / 中 / 高
是否标品：是 / 否
已有证据素材：检测报告 / 买家秀 / 真实评价 / 资质 / 参数表 / 无
平台：淘宝 / 天猫 / 拼多多 / 抖音 / 小红书 / Amazon / Shopify
```

## V2 production workflow

1. Generate the structured brief.
2. Generate platform and traffic adapter.
3. Generate buyer decision map.
4. Generate claim-evidence map.
5. Generate compliance profile.
6. Generate page strategy.
7. Generate copy.
8. Generate visual asset plan.
9. Generate visual system and page prompts.
10. Overlay exact text in a layout/design system.
11. Run conversion, compliance, visual, OCR, and layout QC.
12. Retry only failed pages unless the strategy itself is wrong.
