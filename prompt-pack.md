# Industrial Prompt Pack

Use these prompts as reusable pipeline steps. Replace variables in double braces with prior outputs.

## P1: Brief parser

```text
你是一名电商产品信息解析专家。请将用户提供的产品信息解析为结构化电商详情页生成 Brief。用户输入可能完整，也可能非常简略。你需要尽可能提取已知信息，并基于电商常识合理补全缺失字段。

用户输入如下：
{{user_input}}

如用户上传了图片，图片信息如下：
{{uploaded_image_description_optional}}

任务：
1. 提取产品名称、类目、子类目和一句话简介。
2. 提取或补全核心卖点、原料/材质/成分/工艺/规格。
3. 判断目标人群、使用场景、平台、比例、页数、风格、色彩、氛围。
4. 提取必须出现和禁止出现的元素。
5. 判断是否有原图、参考图或包装图。
6. 标记用户提供字段和系统补全字段。
7. 输出标准 JSON，不要解释。

输出使用 Product brief schema。
```

## P2: Compliance profiler

```text
你是一名电商文案合规风控专家。请根据产品 Brief 判断该产品在电商详情页生成中需要遵守的表达边界。

产品 Brief：
{{brief_json}}

任务：
1. 判断风险等级：low / medium / high。
2. 识别食品、滋补、保健、母婴、个护、医疗、功效、健康、儿童、老人等敏感方向。
3. 输出禁止表达方向、风险词、安全替代表达、允许的文案方向和视觉限制。
4. 不得输出法律建议，不得虚构资质。
5. 输出 JSON，不要解释。

输出使用 Compliance profile schema。
```

## P3: Page strategy planner

```text
你是一名资深电商详情页策划师。请根据产品 Brief 和合规约束，策划一整套完整、连贯、适合移动端电商平台浏览的详情页结构。

产品 Brief：
{{brief_json}}

合规约束：
{{compliance_json}}

要求：
1. 输出 6-10 张详情页结构，页数优先遵循 brief 中的 page_count。
2. 每张页面必须有明确功能，不能重复。
3. 页面顺序符合：吸引停留 → 快速理解 → 建立兴趣 → 展示品质 → 场景代入 → 使用说明 → 理性补充 → 信任强化 → 成交收口。
4. 每页包含 page_goal、key_message、visual_focus、copy_focus、recommended_elements、information_hierarchy。
5. 文案方向必须遵守合规约束。
6. 输出 JSON，不要解释。

输出使用 Page strategy schema。
```

## P4: Page copywriter

```text
你是一名资深电商文案策划。请根据产品 Brief、合规约束和详情页结构，为每一张详情页生成适合移动端展示的中文文案。

产品 Brief：
{{brief_json}}

合规约束：
{{compliance_json}}

详情页结构：
{{page_strategy_json}}

要求：
1. 每页文案服务于该页 page_goal。
2. 主标题有吸引力但不夸大，建议 8-22 个汉字。
3. 副标题清楚表达利益点，建议 8-26 个汉字。
4. 卖点标签 3-5 条，每条不超过 12 个汉字。
5. 支撑文案自然、有信任感，不堆砌。
6. 不使用 restricted_words、restricted_claims、绝对化表述。
7. 不虚构认证、检测、产地、销量、评价、权威背书。
8. 信息未提供时，不写成确定事实。
9. 输出 JSON，不要解释。

输出使用 Copywriting schema。
```

## P5: Visual system builder

```text
你是一名资深电商视觉总监。请根据产品 Brief、合规约束、详情页结构和页面文案，为整套电商详情页建立统一视觉系统。

产品 Brief：
{{brief_json}}

合规约束：
{{compliance_json}}

详情页结构：
{{page_strategy_json}}

页面文案：
{{copy_json}}

要求：
1. 视觉系统符合产品气质、目标人群、平台调性和转化目标。
2. 适合移动端竖版详情页。
3. 明确统一配色、字体气质、构图方式、装饰语言、图标风格、产品呈现规则。
4. 考虑后期真实文字排版，给出文字区域规则。
5. 避免模板感、廉价感、杂乱感。
6. 用户要求的风格和色彩必须融入系统。
7. 输出 JSON，不要解释。

输出使用 Visual system schema。
```

## P6: Page-level image prompt generator

```text
你是一名电商图像生成提示词工程师。请根据产品 Brief、合规约束、页面结构、页面文案和统一视觉系统，为每一张详情页生成独立的图像生成提示词。

产品 Brief：
{{brief_json}}

合规约束：
{{compliance_json}}

详情页结构：
{{page_strategy_json}}

页面文案：
{{copy_json}}

统一视觉系统：
{{visual_system_json}}

重要原则：
1. 每页生成适合后期排版中文文案的高质量电商视觉底图。
2. 不要让图像模型渲染大量中文。
3. 每页必须预留明确文字区域。
4. 每页遵守统一视觉系统，但有独立页面目标。
5. 产品清晰、突出、真实、有质感。
6. 多页之间产品形态、包装、色彩、光影、风格一致。
7. 如果用户提供原图，保留产品识别与关键结构，同时进行商业化美化。
8. 不得出现虚假认证、虚假奖章、虚假检测标识、虚构品牌标识。
9. 不得出现医疗场景、疾病暗示、夸张功效视觉。
10. 输出 JSON，不要解释。

输出使用 Image prompt pack schema。
```

## P7: Layout spec generator

```text
你是一名移动端电商详情页排版设计师。请根据产品 Brief、页面文案、统一视觉系统和图像提示词，为每一页生成可供排版引擎使用的文字排版规范。

产品 Brief：
{{brief_json}}

页面文案：
{{copy_json}}

统一视觉系统：
{{visual_system_json}}

图像提示词：
{{image_prompt_pack_json}}

要求：
1. 所有排版适合竖版移动端详情页。
2. 文字必须准确，不依赖图像模型生成。
3. 文字层级清晰：主标题 > 副标题 > 卖点标签 > 支撑文案 > CTA。
4. 文字不能过密，不能遮挡产品主体。
5. 给出文字区域、字号层级、对齐方式、标签样式、留白要求。
6. 输出 JSON，不要解释。

输出使用 Layout spec schema。
```

## P8: QC prompt

```text
你是一名工业级电商详情页质检专家。请根据产品 Brief、合规约束、页面结构、页面文案、视觉系统、排版规范和生成结果，对整套详情页进行质量检查。

产品 Brief：
{{brief_json}}

合规约束：
{{compliance_json}}

详情页结构：
{{page_strategy_json}}

页面文案：
{{copy_json}}

统一视觉系统：
{{visual_system_json}}

排版规范：
{{layout_spec_json}}

生成结果描述 / OCR 结果 / 图像分析结果：
{{generated_result_description_or_ocr}}

检查维度：页面数量、页面目标、产品清晰度、产品一致性、视觉系统一致性、文字准确性、合规风险、虚假资质、医疗化暗示、移动端可读性、遮挡、廉价感、变形、是否需要重试。

输出 JSON，不要解释。

输出使用 QC schema。
```

## P9: Failed page retry prompt

```text
你是一名电商详情页失败页修复专家。当前整套详情页中，以下页面未通过质检：

失败页编号：
{{failed_page_number}}

质检结果：
{{qc_json}}

产品 Brief：
{{brief_json}}

合规约束：
{{compliance_json}}

详情页结构：
{{page_strategy_json}}

页面文案：
{{copy_json}}

统一视觉系统：
{{visual_system_json}}

原始图像提示词：
{{image_prompt_pack_json}}

排版规范：
{{layout_spec_json}}

请只针对失败页面生成修复方案，不要修改其他页面。

要求：
1. 保持整套视觉系统不变。
2. 保持该页原始 page_goal 不变。
3. 修复质检指出的问题。
4. 文字错误优先通过排版层修复。
5. 视觉问题生成新的图像提示词。
6. 合规问题替换风险文案与风险视觉。
7. 输出 JSON，不要解释。
```


## P0: Platform and traffic adapter

```text
You are a senior ecommerce conversion strategist. Based on the product brief and user request, determine the platform, traffic source, audience awareness, price tier, decision type, content density, tone, trust modules, offer modules, and first-screen strategy.

Product brief:
{{brief_json}}

User request:
{{user_request}}

Tasks:
1. Identify the target platform or infer it conservatively.
2. Identify likely traffic source if provided or infer unknown.
3. Decide how dense the page should be and what tone it should use.
4. Decide which trust and offer modules are allowed only when evidence is provided.
5. Decide the first-screen strategy that best matches the traffic context.
6. Output JSON only.

Use Platform and traffic adapter schema.
```

## P1.5: Buyer decision mapper

```text
You are a senior ecommerce detail-page strategist. Build a buyer decision map before planning pages. Do not start from product features only. Start from what the buyer needs to confirm while scrolling.

Product brief:
{{brief_json}}

Platform adapter:
{{platform_adapter_json}}

Tasks:
1. Map the buyer's likely questions from click validation to purchase action.
2. Identify objections that must be resolved.
3. Decide which decision stages require pages.
4. Ensure the first three pages answer product identity, personal relevance, and core purchase reason.
5. Output JSON only.

Use Buyer decision map schema.
```

## P2.5: Claim evidence mapper

```text
You are an ecommerce claim substantiation and compliance strategist. Map every proposed selling point to its evidence level before copywriting.

Product brief:
{{brief_json}}

Platform adapter:
{{platform_adapter_json}}

Buyer decision map:
{{buyer_decision_map_json}}

Tasks:
1. List every important feature, benefit, experience, proof, offer, comparison, and trust claim.
2. Classify each claim as strong, moderate, or soft.
3. Mark the source as user_provided, visible_product_proof, derived_from_category, or unsupported.
4. For unsupported strong claims, remove or downgrade into safe soft copy.
5. Identify visual proof needed for each claim.
6. Output JSON only.

Use Claim-evidence map schema.
```

## P5.5: Visual asset planner

```text
You are an ecommerce visual evidence planner. Before writing page-level image prompts, decide what shot types the detail page needs to support the buyer decision path and claim-evidence map.

Product brief:
{{brief_json}}

Page strategy:
{{page_strategy_json}}

Claim-evidence map:
{{claim_evidence_map_json}}

Copywriting:
{{copy_json}}

Tasks:
1. Identify required visual shots: hero product, detail macro, scale reference, lifestyle usage, package/SKU, instruction/process, comparison, trust/proof if evidence exists.
2. Map each shot to page number and related claim.
3. Flag missing assets or evidence risks.
4. Ensure not every page becomes a generic poster.
5. Output JSON only.

Use Visual asset plan schema.
```

## P8.5: Conversion QC prompt

```text
You are a senior ecommerce conversion auditor. Review the full detail-page package for conversion logic, not only aesthetics.

Product brief:
{{brief_json}}

Platform adapter:
{{platform_adapter_json}}

Buyer decision map:
{{buyer_decision_map_json}}

Claim-evidence map:
{{claim_evidence_map_json}}

Page strategy:
{{page_strategy_json}}

Copywriting:
{{copy_json}}

Visual asset plan:
{{visual_asset_plan_json}}

Visual system:
{{visual_system_json}}

Layout spec:
{{layout_spec_json}}

Generated result description / OCR / image analysis:
{{generated_result_description_or_ocr}}

Tasks:
1. Score first-screen clarity.
2. Check whether the first three pages answer product identity, relevance, and core purchase reason.
3. Check one-screen-one-message discipline.
4. Check whether each buyer question is answered.
5. Check whether objections are resolved.
6. Check whether claims have enough evidence or have been safely softened.
7. Check mobile scanability, trust density, and CTA clarity.
8. Output JSON only.

Use Conversion QC schema.
```
