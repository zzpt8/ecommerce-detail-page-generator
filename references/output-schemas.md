# 输出 Schema

使用这些 schema 保持输出结构化、可复用、可被系统消费。字段名保留英文，字段说明和取值语义用中文理解。

## 1. Product brief schema

```json
{
  "product_info": {
    "product_name": "产品名称",
    "product_category": "产品大类",
    "product_subcategory": "产品子类",
    "product_description": "产品简介",
    "source_confidence": "high | medium | low"
  },
  "selling_info": {
    "core_selling_points": [
      {
        "point": "卖点",
        "source": "user_provided | auto_generated",
        "confidence": "high | medium | low"
      }
    ],
    "supporting_details": [],
    "price_positioning": "low | mid | high | unknown"
  },
  "material_or_ingredient_info": {
    "ingredients_or_materials": [],
    "process_or_craft": [],
    "specifications": {
      "weight": "",
      "volume": "",
      "size": "",
      "quantity": "",
      "package_type": "",
      "sku_info": []
    }
  },
  "audience_info": {
    "target_audience": "",
    "age_range": "",
    "gender": "",
    "persona": "",
    "preferences": [],
    "pain_points": [],
    "purchase_motivations": []
  },
  "scenario_info": {
    "usage_scenarios": [],
    "emotional_scenarios": [],
    "platform_scenarios": []
  },
  "visual_requirements": {
    "preferred_style": [],
    "preferred_colors": [],
    "image_mood": [],
    "must_show_elements": [],
    "must_not_show_elements": [],
    "reference_image_usage": "none | product_material | style_reference | packaging_reference"
  },
  "platform_requirements": {
    "platform": "",
    "page_ratio": "9:16",
    "page_count": 8,
    "mobile_first": true
  },
  "copy_requirements": {
    "copy_mode": "auto_generate | user_provided | mixed",
    "tone": "",
    "must_include_copy": [],
    "avoid_copy": []
  },
  "risk_flags": {
    "potential_high_risk_category": false,
    "risk_reasons": []
  },
  "missing_fields": [],
  "auto_completion_notes": []
}
```

## 2. Compliance profile schema

```json
{
  "compliance_profile": {
    "risk_level": "low | medium | high",
    "sensitive_category_flags": [],
    "reason": []
  },
  "restricted_claims": [
    {
      "claim_type": "",
      "description": "",
      "examples_to_avoid": []
    }
  ],
  "restricted_words": [],
  "absolute_words_to_avoid": ["最", "第一", "顶级", "永久", "根治", "立刻见效", "100%", "保证"],
  "safe_expression_rules": [
    {
      "rule": "",
      "example": ""
    }
  ],
  "suggested_safe_expressions": [],
  "replacement_map": [
    {
      "risky_expression": "",
      "safe_replacement": ""
    }
  ],
  "allowed_copy_directions": [],
  "forbidden_copy_directions": [],
  "notes_for_copywriter": [],
  "notes_for_visual_generation": []
}
```

## 3. Page strategy schema

```json
{
  "page_strategy": {
    "page_count": 8,
    "conversion_logic": "详情页整体转化逻辑",
    "overall_storyline": "从首屏到收口的整体叙事",
    "recommended_page_ratio": "9:16",
    "platform_fit_notes": []
  },
  "pages": [
    {
      "page_number": 1,
      "page_type": "",
      "page_goal": "",
      "conversion_role": "",
      "key_message": "",
      "content_focus": "",
      "visual_focus": "",
      "recommended_scene": "",
      "recommended_elements": [],
      "copy_focus": "",
      "information_hierarchy": {
        "primary": "",
        "secondary": "",
        "tertiary": []
      },
      "must_avoid": [],
      "notes_for_next_step": ""
    }
  ]
}
```

## 4. Copywriting schema

```json
{
  "copywriting_strategy": {
    "tone": "",
    "copy_angle": "",
    "audience_emotion": "",
    "compliance_summary": ""
  },
  "pages": [
    {
      "page_number": 1,
      "page_type": "",
      "main_title": "",
      "sub_title": "",
      "selling_points": [],
      "supporting_copy": "",
      "badge_texts": [],
      "cta_text": "",
      "notes_for_typesetting": {
        "title_priority": "high | medium | low",
        "text_density": "low | medium | high",
        "suggested_layout": ""
      },
      "compliance_check": {
        "pass": true,
        "risk_level": "low | medium | high",
        "risky_phrases_removed": []
      }
    }
  ]
}
```

## 5. Visual system schema

```json
{
  "visual_system": {
    "overall_style": "",
    "brand_mood": "",
    "audience_fit": "",
    "platform_fit": "",
    "color_palette": {
      "primary_colors": [],
      "secondary_colors": [],
      "accent_colors": [],
      "background_colors": [],
      "color_usage_rules": []
    },
    "typography_style": {
      "title_style": "",
      "subtitle_style": "",
      "body_style": "",
      "badge_style": "",
      "font_mood": ""
    },
    "layout_system": {
      "grid": "",
      "safe_margin": "",
      "common_compositions": [],
      "text_area_rules": [],
      "product_area_rules": []
    },
    "decoration_language": {
      "shapes": [],
      "icons": "",
      "stickers": "",
      "light_effects": "",
      "texture": "",
      "illustration_style": ""
    },
    "product_presentation_rules": {
      "product_scale": "",
      "product_angle": "",
      "product_lighting": "",
      "product_consistency_rules": [],
      "detail_shot_rules": []
    },
    "scene_rules": {
      "background_type": "",
      "scene_elements": [],
      "depth_of_field": "",
      "lifestyle_level": "",
      "avoid_scene_elements": []
    },
    "page_consistency_rules": [],
    "negative_visual_rules": []
  }
}
```

## 6. Image prompt pack schema

```json
{
  "image_prompt_pack": {
    "global_style_anchor": "全局风格锚点",
    "global_consistency_rules": [],
    "pages": [
      {
        "page_number": 1,
        "page_type": "",
        "image_prompt_cn": "",
        "image_prompt_en": "",
        "negative_prompt_cn": "",
        "negative_prompt_en": "",
        "composition_instruction": "",
        "reserved_text_area": "",
        "product_instruction": "",
        "background_instruction": "",
        "lighting_instruction": "",
        "style_anchor": "",
        "consistency_anchor": "",
        "render_priority": ["product clarity", "commercial quality", "layout readability"],
        "post_layout_notes": ""
      }
    ]
  }
}
```

## 7. Layout spec schema

```json
{
  "layout_spec": {
    "canvas": {
      "ratio": "9:16",
      "recommended_size": "1080x1920",
      "safe_margin": {
        "top": "6%",
        "bottom": "6%",
        "left": "6%",
        "right": "6%"
      }
    },
    "global_typography": {
      "main_title": {"font_weight": "bold", "relative_size": "large", "line_height": "1.1-1.2"},
      "sub_title": {"font_weight": "medium", "relative_size": "medium", "line_height": "1.2-1.35"},
      "selling_points": {"font_weight": "medium", "relative_size": "small-medium", "style": "badge"},
      "supporting_copy": {"font_weight": "regular", "relative_size": "small", "line_height": "1.4-1.6"}
    },
    "pages": [
      {
        "page_number": 1,
        "page_type": "",
        "text_blocks": [
          {
            "block_type": "main_title | sub_title | selling_point | supporting_copy | badge | cta",
            "content": "",
            "position": {"x": "", "y": "", "width": "", "height": ""},
            "alignment": "left | center | right",
            "style": {"font_mood": "", "color": "", "background": "", "border_radius": "", "shadow": "", "decoration": ""},
            "priority": "high | medium | low"
          }
        ],
        "avoid_overlap_area": "",
        "notes_for_designer": ""
      }
    ]
  }
}
```

## 8. QC schema

```json
{
  "overall_qc": {
    "pass": true,
    "score": 90,
    "summary": "",
    "critical_issues": [],
    "recommended_action": "approve | minor_fix | retry_some_pages | retry_all"
  },
  "page_qc": [
    {
      "page_number": 1,
      "pass": true,
      "score": 90,
      "issues": [
        {
          "issue_type": "copy | visual | layout | compliance | consistency | product | platform",
          "severity": "low | medium | high | critical",
          "description": "",
          "evidence": "",
          "suggested_fix": ""
        }
      ],
      "retry_needed": false,
      "retry_reason": "",
      "fix_priority": "low | medium | high"
    }
  ],
  "compliance_qc": {"pass": true, "risky_phrases": [], "risky_visuals": [], "required_replacements": []},
  "copy_accuracy_qc": {"pass": true, "ocr_mismatch": [], "missing_text": [], "extra_text": []},
  "visual_consistency_qc": {"pass": true, "inconsistent_pages": [], "style_drift_notes": []}
}
```

## 9. Platform and traffic adapter schema

```json
{
  "platform_adapter": {
    "platform": "taobao | tmall | pinduoduo | douyin | xiaohongshu | amazon | dtc_shopify | unknown",
    "traffic_source": "search | recommendation_feed | short_video | livestream | paid_ad | private_domain | social_note | unknown",
    "audience_awareness": "cold | problem_aware | product_aware | comparison | ready_to_buy | unknown",
    "price_tier": "low | mid | high | unknown",
    "product_decision_type": "impulse | considered | high_risk | repeat_purchase | gift | unknown",
    "content_density": "low | medium | high",
    "tone_direction": "",
    "visual_density": "low | medium | high",
    "trust_modules_allowed": [],
    "trust_modules_blocked_without_evidence": [],
    "offer_modules": [],
    "page_length_guidance": "",
    "first_screen_strategy": "",
    "platform_notes": []
  }
}
```

## 10. Buyer decision map schema

```json
{
  "buyer_decision_map": {
    "overall_purchase_path": "",
    "first_three_page_requirement": {
      "product_identity_answered": false,
      "personal_relevance_answered": false,
      "core_purchase_reason_answered": false
    },
    "decision_stages": [
      {
        "stage": "attention | relevance | value | differentiation | proof | usage | risk_reduction | trust | action",
        "buyer_question": "",
        "objection_to_resolve": "",
        "content_answer": "",
        "evidence_needed": [],
        "page_needed": true,
        "priority": "high | medium | low"
      }
    ]
  }
}
```

## 11. Claim-evidence map schema

```json
{
  "claim_evidence_map": {
    "summary": "",
    "unsupported_claim_policy": "downgrade_to_soft_language_or_remove",
    "claims": [
      {
        "claim": "",
        "claim_type": "feature | benefit | experience | proof | offer | comparison | trust",
        "source": "user_provided | visible_product_proof | derived_from_category | unsupported",
        "claim_strength": "strong | moderate | soft",
        "evidence_required": true,
        "evidence_available": false,
        "allowed_customer_copy": "",
        "blocked_customer_copy": [],
        "visual_proof": "",
        "risk_note": "",
        "page_role": ""
      }
    ],
    "missing_evidence": [
      {
        "desired_claim": "",
        "evidence_needed": "",
        "safe_alternative": ""
      }
    ]
  }
}
```

## 12. Visual asset plan schema

```json
{
  "visual_asset_plan": {
    "global_asset_strategy": "",
    "required_shots": [
      {
        "shot_type": "hero_product | scale_reference | detail_macro | lifestyle_usage | package_sku | instruction_process | comparison | trust_proof | texture_mood",
        "purpose": "",
        "related_claims": [],
        "source_requirement": "product_image | reference_image | generated_scene | user_provided_proof | not_required",
        "priority": "high | medium | low",
        "risk_if_missing": ""
      }
    ],
    "page_asset_mapping": [
      {
        "page_number": 1,
        "primary_shot_type": "",
        "supporting_shot_types": [],
        "text_safe_area_needed": "",
        "product_identity_requirement": ""
      }
    ],
    "reference_image_priority": "product_identity > packaging_label > visible_material > style_reference",
    "missing_asset_risks": []
  }
}
```

## 13. Conversion QC schema

```json
{
  "conversion_qc": {
    "overall_conversion_score": 90,
    "summary": "",
    "first_screen_clarity": {"score": 0, "notes": ""},
    "first_three_pages": {"score": 0, "notes": ""},
    "one_screen_one_message": {"score": 0, "notes": ""},
    "buyer_question_coverage": {"score": 0, "missing_questions": []},
    "objection_handling": {"score": 0, "unresolved_objections": []},
    "evidence_strength": {"score": 0, "weak_or_unsupported_claims": []},
    "mobile_scanability": {"score": 0, "notes": ""},
    "trust_density": {"score": 0, "notes": ""},
    "cta_clarity": {"score": 0, "notes": ""},
    "page_level_conversion_issues": [
      {
        "page_number": 1,
        "issue": "",
        "severity": "low | medium | high | critical",
        "suggested_fix": ""
      }
    ]
  }
}
```
