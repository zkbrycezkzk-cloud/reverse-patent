# lib-patent-reverse-layout Version Module

## Current Version

v1.4.3

## Release Date

2026-05-22

## Version Meaning

`v1.4.3` adds a LATP cathode-additive reverse-layout module derived from a full measured/predictive LATP workflow. It shifts LATP cases away from slurry physical properties and toward LATP body parameters, cathode additive content, electrode parameters, and cell performance; it also clarifies final-application table cleanup and deterministic safety-result wording. `v1.4.2` made claim 1 default to a performance-parameter combination layout when measured material, electrode/structure, and performance data are provided. `v1.4.1` added a post-Compile final-draft optimization module derived from a measured cylindrical lithium-ion cell reverse-layout case.

## Source Compatibility

| Source | Role |
|---|---|
| `lib-patent-reverse-layout v1.0` | Primary workflow: measured-product reverse layout, data-centering ranges, staged confirmation |
| `lib-patent-refiner-v2.2` | Reference library: CNIPA drafting rules, embodiment variation wording, test standards, reverse identification, mechanism analysis |

## Change Summary

1. Upgraded `SKILL.md` into a comprehensive measured-data-driven reverse patent drafting entrypoint.
2. Added mandatory output requirements for Step 1 through Step 4.
3. Added reverse-measurability scoring before claim drafting.
4. Strengthened the data-centering method for claim ranges.
5. Integrated reference links to `reverse_patent_layout.md`, `full_spec_expansion_v2_2.md`, `example_variation.md`, `test_standards.md`, `material_process.md`, and `mechanism_analysis.md`.
6. Kept `lib-patent-refiner-v2.2` read-only and independent.
7. Added `references/performance_structure_coupling_workflow.md` for "performance joint constraints + structural joint conditions" claims.
8. Added default Z1/Z2 position definitions for electrode active-material layers.
9. Added guidance for using prophetic competitor epsilon/lambda data only with explicit user confirmation and `[P]` marking.

10. Added `references/attachment_style_rewrite_workflow.md` for mapping a complete application draft into an attachment/template `.docx` while preserving heading structure, table layout, and patent-agent writing style.
11. Added `Reverse_AttachmentRewrite` as an optional post-Compile command.
12. Strengthened performance-explanation style: use table-driven, variable-by-variable comparisons with data changes, mechanism, and claim-range conclusion.
13. Changed `Reverse_Compile` default output to `[主题]_最终申请稿.md` and removed document-rendering requirements from the Compile stage.
14. Added `references/reverse_compile_markdown_output.md` for Markdown title structure, output naming, table rules, and Compile self-checks.
15. Added a reusable high-rate platform-voltage-difference test method to `references/reverse_perftest_methods.md`, including low-rate reference platform, 10A/20A/30A/35A/40A discharge curves, `Delta V_I`, `S20-40`, auxiliary 40A temperature recording, structure-parameter review, and data-validity checks.
16. Clarified that 40A temperature is auxiliary unless the user explicitly selects temperature rise as the core invention route; the default platform-voltage-difference method does not rely on cooling-fit or heat-dissipation calibration models.
17. Added `references/final_draft_optimization_patterns.md` for post-Compile final-draft optimization, including detailed embodiment 1 preparation routes, concrete "本例与实施例1的区别在于" variation wording, variable-by-variable "对比实施例……与对比例……可知" mechanism paragraphs, single unknown-cell reverse-identification flow, and voltage-interval silicon-capacity-share calculation.
18. Added optional `Reverse_FinalDraftOptimize` guidance in `SKILL.md`; it is used after Compile or when the user asks to integrate final draft revision experience into the skill, without changing the confirmed independent-claim core unless explicitly instructed.
19. Added a claim-1 default rule for measured-data cases: use “performance joint constraints + material/electrode parameter joint conditions + coordinated relationship” unless the user explicitly selects another independent-claim route.
20. Clarified that measured values must be embedded in centered claim intervals before drafting examples or test sections.
21. Clarified that version history stays in `VERSION.md`; `SKILL.md` should only point to the version module and should not duplicate changelog content.
22. Added `references/latp_cathode_additive_workflow.md` for LATP positive-electrode additive cases, including D10/D50/D90, D90/D50, NASICON phase content, Li/Al/Ti/P ratio, Karl Fischer water, magnetic impurities, BET, tap density, ionic conductivity, Ti3+/Ti4+, area-fraction deviation, `M=(D90/D50)*W/C`, `Q=R*A/C`, predictive-data marking, final table cleanup, heat-box deterministic wording, and avoidance of LATP substrate, SiF4 coating, LAGP/Ge shell, Ga-LLZO/LATP/CNT, and LATP-CeO2 routes.
23. Clarified that final application tables should not retain internal management columns such as data-identification, avoidance type, or proof target columns.

## Compatibility Notes

- Existing `Reverse_Intake`, `Reverse_Claims`, `Reverse_Examples`, `Reverse_Perftest`, `Reverse_IdentifyTest`, `Reverse_Compile`, and `Reverse_Audit` command names remain valid.
- `Reverse_FinalDraftOptimize` is optional and post-Compile oriented; it does not replace the staged confirmation workflow.
- New `Reverse_AttachmentRewrite` is optional and only runs after Compile or when the user provides a complete draft to rewrite.
- `Reverse_Compile` now defaults to Markdown output. Use `Reverse_AttachmentRewrite` when a user-provided attachment or template must be preserved as a formatted document.
- The workflow is stricter than v1.0: every stage must stop for explicit user confirmation.
- Product claims should prioritize reverse-measurable parameters; pure performance claims should normally be dependent claims or specification support.
- For high-rate low-temperature-rise cases, independent claims may use coordinated formulas such as `Delta V` plus `Ts` with `epsilon(Z1)-epsilon(Z2)` plus `lambda(Z2)-lambda(Z1)`, provided Z1/Z2 and test methods are explicitly defined.
- For measured material/electrode/performance cases, claim 1 should expose the performance constraints, parameter constraints, and coordinated relationship as separate readable clauses so the user can confirm the layout before Step 2.
