# 工业级提示词包

本文件提供可复用的提示词模板，用于把商品信息转化为详情页生成工作流。使用时将占位符替换为用户产品信息，并根据平台和类目读取对应参考文件。

## 1. 产品 Brief 解析提示词

```text
你是一名电商详情页策略师。请将以下产品信息整理为结构化产品 brief。保留用户明确提供的事实；缺失信息保守推断并标记为 assumption；不要虚构参数、认证、产地、销量、评价、功效或品牌事实。

产品信息：
{{product_info}}

请输出：
1. 产品基础信息
2. 核心卖点及来源
3. 材质/成分/规格信息
4. 目标人群和痛点
5. 使用场景
6. 视觉需求
7. 平台要求
8. 文案要求
9. 风险标记和缺失字段
```

## 2. 平台与流量适配提示词

```text
你是一名电商平台策略师。请根据产品 brief、平台和流量来源，判断详情页应采用的信息密度、语气、视觉密度、信任模块、优惠模块、页面长度和首屏策略。

输入：
产品 brief：{{brief}}
平台：{{platform}}
流量来源：{{traffic_source}}
用户阶段：{{audience_awareness}}
价格带：{{price_tier}}

要求：
- 区分淘宝/天猫、拼多多、抖音、小红书、Amazon A+、Shopify。
- 不要因为平台风格而虚构事实。
- 输出平台适配结论和注意事项。
```

## 3. 买家决策路径提示词

```text
你是一名转化型详情页策划。请先不要规划页面，而是基于产品 brief 和平台适配，建立买家决策路径。

输入：
产品 brief：{{brief}}
平台适配：{{platform_adapter}}

请按以下阶段输出：attention、relevance、value、differentiation、proof、usage、risk_reduction、trust、action。
每个阶段说明：
- 买家问题
- 需要解决的异议
- 内容回答
- 需要的证据
- 是否需要页面
- 优先级

特别检查：前三页必须回答“产品是什么、为什么与我相关、为什么值得买”。
```

## 4. 卖点-证据映射提示词

```text
你是一名电商合规与证据审核专家。请对产品卖点进行证据映射，不要直接写面向买家的强文案。

输入：
产品 brief：{{brief}}
用户提供证据：{{proof_assets}}
产品图片可见信息：{{visible_product_proof}}

对每个主张输出：
- claim
- claim_type
- source
- claim_strength
- evidence_required
- evidence_available
- allowed_customer_copy
- blocked_customer_copy
- visual_proof
- risk_note
- page_role

规则：
强主张没有用户证据时必须删除或降级；不要创造认证、检测、奖项、销量、专家、医生、平台或政府背书。
```

## 5. 合规画像提示词

```text
你是一名电商文案合规审核员。请根据产品类目和卖点证据映射，生成合规画像。

输入：
产品类目：{{category}}
卖点证据映射：{{claim_evidence_map}}
平台：{{platform}}

请输出：
- 风险等级
- 敏感类目标记
- 禁止主张类型
- 禁止词和绝对化词
- 安全表达规则
- 推荐安全表达
- 风险表达替代
- 文案注意事项
- 视觉生成注意事项
```

## 6. 页面策略提示词

```text
你是一名工业级电商详情页策划。请基于 brief、平台适配、买家决策路径、卖点证据映射和合规画像，规划 {{page_count}} 页竖版详情页。

要求：
- 一页一个主要买家问题。
- 页面顺序符合转化路径。
- 前三页必须完成产品身份、相关性和核心购买理由。
- 每页说明 page_goal、conversion_role、key_message、content_focus、visual_focus、recommended_scene、recommended_elements、copy_focus、information_hierarchy、must_avoid。
```

## 7. 逐页文案提示词

```text
你是一名中文电商文案。请根据页面策略和合规画像写逐页文案。

要求：
- 主标题 8-22 个中文字符。
- 副标题 8-26 个中文字符。
- 卖点 3-5 个，适合手机端标签。
- 避免医疗、绝对化、无证据对比、虚假资质、虚假参数。
- 每页输出 main_title、sub_title、selling_points、supporting_copy、badge_texts、cta_text、typesetting notes、compliance_check。
```

## 8. 视觉资产规划提示词

```text
你是一名电商视觉制片。请在写图像提示词之前规划必需镜头。

输入：
页面策略：{{page_strategy}}
卖点证据映射：{{claim_evidence_map}}
产品图/参考图：{{reference_images}}

输出：
- 全局视觉资产策略
- required_shots：主视觉、比例参照、细节特写、生活场景、包装/SKU、使用步骤、对比、信任证据、质感氛围
- page_asset_mapping
- 缺失资产风险
```

## 9. 统一视觉系统提示词

```text
你是一名电商视觉系统设计师。请为整套详情页建立统一视觉系统。

输入：
产品 brief：{{brief}}
页面策略：{{page_strategy}}
视觉偏好：{{visual_preferences}}
平台：{{platform}}

输出：
- overall_style
- brand_mood
- color_palette
- typography_style
- layout_system
- decoration_language
- product_presentation_rules
- scene_rules
- page_consistency_rules
- negative_visual_rules

要求：视觉系统必须支持转化路径，不要只追求好看。
```

## 10. 逐页图像生成提示词

```text
你是一名电商 AI 出图提示词工程师。请为每一页生成适合图像模型的提示词。

输入：
页面策略：{{page_strategy}}
逐页文案：{{copywriting}}
视觉资产规划：{{visual_asset_plan}}
视觉系统：{{visual_system}}
参考图：{{reference_images}}

要求：
- 每页一条中文提示词和一条英文提示词。
- 重点生成干净商业视觉和文字安全区域。
- 不要求模型直接生成大段中文。
- 加入 negative prompt，规避乱码、假资质、logo、水印、医疗场景、产品变形、廉价拼贴。
- 明确 composition、reserved_text_area、product_instruction、background_instruction、lighting_instruction、style_anchor 和 post_layout_notes。
```

## 11. 排版规范提示词

```text
你是一名移动端电商设计排版师。请根据逐页文案和视觉提示词，给出后期叠字排版规范。

输出：
- 画布尺寸和安全边距
- 全局字体层级
- 每页文字块：类型、内容、位置百分比、宽高、对齐、样式、优先级
- 产品避让区域
- 设计师注意事项

要求：保证手机端可读，不遮挡产品核心信息。
```

## 12. 质检与重试提示词

```text
你是一名电商详情页质检负责人。请根据页面策略、文案、视觉结果和合规边界进行质检。

检查：
- 页面结构
- 产品准确性
- 合规
- 文案质量
- 视觉质量
- 移动端可读性
- 多页一致性
- 转化路径

输出：
- overall_qc
- page_qc
- compliance_qc
- copy_accuracy_qc
- visual_consistency_qc
- conversion_qc
- 失败页重试方案

原则：只重试失败页，除非视觉系统、产品身份或页面策略整体错误。
```
