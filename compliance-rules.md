# Compliance Rules for Ecommerce Detail Pages

These rules are practical generation constraints, not legal advice. Use them to reduce risk when generating ecommerce copy and visuals.

## Universal restrictions

Do not invent or imply:

- certifications, inspections, test reports, patents, awards, licenses, or official approvals
- sales volume, ranking, market share, repeat purchase rate, or customer review facts
- celebrity, doctor, institution, expert, platform, or government endorsement
- exact origin, production process, grade, year, batch, or supplier facts unless user provided them
- absolute superiority such as "全网第一", "最有效", "永久", "100%", "保证"

Avoid these copy directions unless substantiated by the user and allowed for the category:

- disease prevention or treatment
- physiological function improvement
- guaranteed results
- before/after transformation claims
- attack-style comparisons with competitors
- fear-driven urgency that implies harm if not purchased

## High-risk categories

Use strict mode for:

- food, beverage, tonic ingredients, tea, nutrition, dietary products
- health, wellness, elderly, maternity, infant, children
- skincare, personal care, hair care, oral care
- cleaning products with antibacterial/disinfection claims
- medical devices, medicines, rehabilitation, pain relief, sleep, weight loss

## Food / beverage / tonic ingredient rules

Avoid claims such as:

- 治疗, 预防, 改善, 调理, 修复身体
- 增强免疫力, 提高抵抗力
- 补气, 养血, 祛湿, 降火, 护肝, 养肾
- 缓解疲劳, 改善睡眠, 改善体虚
- 药食同源 as a selling proof unless user explicitly provides compliant context
- 老少皆宜, 孕妇可用, 儿童可用 unless user provides qualification

Safer directions:

- 日常泡饮
- 自然原材
- 温暖陪伴
- 轻松搭配
- 家庭常备
- 日常饮养氛围
- 一杯热饮的生活仪式感
- 适合居家、办公、户外小憩等场景

Risky-to-safe replacements:

| Risky expression | Safer replacement |
| --- | --- |
| 补气养血 | 日常温和饮养 |
| 增强免疫力 | 给日常生活一点温暖补给 |
| 改善疲劳 | 忙碌之后的一杯暖饮陪伴 |
| 调理身体 | 轻松融入日常饮用习惯 |
| 体虚人群适用 | 适合喜欢日常饮养的人群 |
| 药材级品质 | 原材质感看得见 |
| 功效显著 | 体验更安心、更日常 |

## Skincare and personal care rules

Avoid:

- 根治, 治疗, 医美级疗效, 药用疗效
- 永久祛斑, 彻底祛痘, 修复皮肤屏障 as guaranteed claim
- 100%不过敏, 孕妇绝对安全
- before/after images that imply medical cure

Safer directions:

- 清爽肤感
- 温和护理
- 日常清洁
- 细腻质地
- 使用体验
- 肤感舒适
- 清洁更省心

## Maternal / infant rules

Avoid:

- 绝对安全, 零风险, 医生推荐 unless provided and lawful
- 治疗湿疹, 改善发育, 提升智力
- exaggerated fear tactics

Safer directions:

- 柔软亲肤
- 日常照护
- 细致呵护
- 使用更省心
- 家庭场景友好

## Cleaning product rules

Avoid:

- 100%杀菌, 永久防霉, 彻底除菌 unless substantiated
- health protection claims beyond cleaning use

Safer directions:

- 日常清洁更方便
- 家庭打理更省心
- 清爽洁净感
- 适合厨房、浴室、客厅等场景

## Electronics and appliances rules

Avoid:

- false specs, fake compatibility, fake certification
- permanent durability promises
- unsupported performance rankings

Safer directions:

- 使用更便捷
- 连接更顺手
- 体验更稳定
- 适配常见场景
- 参数以用户提供信息为准

## Visual restrictions

Avoid:

- hospital, doctor, medicine bottle, medical cross, diagnostic chart, organs, pain points, or disease imagery for ordinary food/wellness products
- fake certification badges, inspection seals, award medals, ranking crowns
- extreme before/after comparisons
- unauthorized platform logos, celebrity faces, famous brand packaging, watermarks
- visual elements that imply children/pregnant/elderly use if user did not provide evidence

## Compliance output rule

Always include a compliance note for medium/high-risk categories. Example:

"本方案采用生活方式与日常使用表达，已规避治疗、改善身体机能、绝对化承诺和虚构资质类表述。"


## Evidence-driven compliance layer

Use `claim-evidence-rules.md` before customer-facing copy. Compliance is not only about banned words; it is also about whether a claim has enough support.

### Claim strength gate

- Strong claims require explicit user-provided evidence.
- Moderate claims require either user-provided facts, visible product proof, or cautious wording.
- Soft claims may be generated from scenario and experience, but must not imply guaranteed effects.

### Always require user-provided evidence for

- certifications, inspections, test reports, patents, awards, licenses, official approvals
- sales volume, ranking, market share, repeat purchase rate, customer review facts
- celebrity, doctor, institution, expert, platform, or government endorsement
- exact origin, production process, grade, year, batch, supplier facts
- medical, health, physiological, disinfecting, antibacterial, waterproof, safety, compatibility, durability, or performance claims when specific or measurable

### Safe output rule

If a claim is attractive but unsupported:

1. Do not write it as a customer-facing fact.
2. Add it to missing evidence.
3. Provide a soft safe alternative.
4. Use visual detail, scenario, or lifestyle language instead of proof language.

### Visual compliance rule

Do not create visual proof that the user did not provide. In particular, do not generate:

- certificate cards, inspection seals, official stamps, medals, award badges
- doctor/hospital/lab scenes for ordinary consumer goods
- fake buyer review screenshots or fake chat screenshots
- ranking crowns, platform logo endorsements, government-like emblems
- before/after transformation visuals for unsupported efficacy
