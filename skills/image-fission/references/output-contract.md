# 任务记录与交接

这是执行记录，不是已部署 API。保存在当前任务的私有输出目录，不随 Skill 发布。使用原 task_id 和 variant_id，跨消息继续累计。下例是结构说明；实际资产必须填真实路径/ID，不能用占位冒充结果。

```json
{
  "schema_version": 1,
  "task_id": "stable-task-id",
  "reference_authority": {"composition": "source-asset", "identity": "person-original", "product": "product-original"},
  "preserve": ["outfit", "makeup"],
  "replace": ["face", "product"],
  "budget": {"planned_outputs": 1, "max_extra_calls": 2, "max_rounds_per_target": 3, "explicit_override": null},
  "targets": [{"variant_id": "size_m", "rounds_used": 0, "best_result": null, "model_review": "pending", "user_acceptance": "pending"}],
  "calls": [],
  "status": "planned"
}
```

每条 calls 写：target、round、model（未知如实记）、base_asset、original_references、changed_dimensions、preserved_dimensions、request_id/generation_id（有才填）、status（pending/completed/technical_failed）、actual_result、quality_findings、billing（未知用 null）。不存密钥、签名 URL；生成引用可以存稳定对象 ID。

调用前检查目标轮数、整批初始/追加次数、费用授权与 pending；提交后立即记 ID。完成后实际查看再写检查项与最佳图。更换提示词、用户换聊天或再次说“不像”不自动重置计数；明确新任务/新预算才新增阶段，保留前史。技术失败保留提交/收费记录，不混入已完成图的质量轮数，也不自动补发费用。

最终状态 completed/partial/needs_model_decision/technical_blocked/planned 如实选择。所有目标实际完成且已自检才 completed；部分缺图或未通过用 partial。移交视频导演时传选定首帧、原产品/人物参考、明确的产品种类数量与初始状态、未解决项；冲突不能交给视频瞬变纠正。
