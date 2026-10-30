# Release Notes

## v1.2.3
GH#1100 consumer wave batch 6 — declare the data flow these steps were resolving positionally. 4 binding(s) added.

Two bindings do not take the positional predecessor. `create-content-brief` (slot "Topic") binds Campaign Planning — position would have fed it the already-written copy. `polish-language` (slot "Source") binds Copywriting — position would have fed it a consistency *verdict*, which is a decision rather than text.

## v1.2.2
GH#1044 — the last of the required-but-undocumented inputs, resolved by testing whether the existing table name is itself required by a prompt rather than by how similar the names look. documented target_market. Rows generated from the requiring prompt's own declared description, example and required flag. No behaviour change; documentation only.

## v1.2.1
GH#1044 — document the inputs this workflow's prompts REQUIRE but its Inputs table never listed. A user supplying exactly what the table asked for was running with required parameters unsatisfied — a silent wrong run, not a documentation nicety. documented 2 input(s): campaign_name, target_market. Every row is generated from the requiring prompt's own declared description, example and required flag — none invented. No behaviour change; documentation only.

## v1.2.0
GH#863 (K-045 intent/output-mismatch) — wire the previously-orphaned `campaign-brief-generator` prompt into the pipeline. It was declared but never invoked, so the campaign brief it promises was never produced and copywriting silently consumed the campaign plan instead. Added a `campaign-brief-builder` backing skill (title "Campaign Brief Generator") and inserted the brief step at Stage 3 (after campaign planning, before copywriting), bound to the campaign plan and audience segments via explicit `from_step`. Rebound copywriting to consume the brief step's output, and converted positional `{{steps.X.output}}` refs in plan-campaign, campaign-brief-generator, and write-copy to `context_params` + `{{step.context.*}}` bindings. Added a Stage 5 narrative for the content-enrichment/QA steps. Contents: skills 2→3, total 9→10.

## v1.1.29
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.1.28
GH#745 — declare per-step `output: {name, type}` on every execution step (campaign_brief/text, campaign_plan/text, copy/text, brief/text, ideas/list, image_brief/text, consistency_verdict/decision, polished_content/text). Lights up the #744 rich flow-map with named, typed outputs. Content-only; no bindings or logic changes.

## v1.1.27
GH#645 Row 3 final — re-pin 6 prompt-deps to the new v1.0.2/v1.0.3 versions that now expose `nodes[].content` via /api/shared/<slug>/<v>/metadata (per GH#651 endpoint extension + d1Execute dual-mode fix). Engine validator's dep-aware loop-body `{{loop.item}}` interpolation check + binding from_step resolution now pass through deps for this consumer. No content changes; identity + dep-version repin only.

## v1.1.26
GH#645 Row 3b — migrate to K-037 dep-referenced schema. Strip 15 inline shared-content files and declare 15 hub-shared deps (UUID id + slug name + version + checksum from `gen-dep-checksums.mjs`). Closes pre-Step-3 inline-vendoring for this bundle.

## v1.1.25
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.24
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.23
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.22
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.21
Initial catalog release with full structural and content-quality validation. All scanner checks pass.
