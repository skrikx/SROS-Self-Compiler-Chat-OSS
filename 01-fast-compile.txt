# File: examples/01-fast-compile.txt

# SROS Self-Compiler (OSS) - Example 01: Fast mode
# Goal: show the shortest possible user input and the expected output root.

USER
compile: build a 10 page enterprise AI agency website for PlatXP (USA), cobalt blue aesthetic, include sitemap + copy brief, stack SvelteKit + Tailwind + Motion One

ASSISTANT (expected)
<promptunit_package xmlns="https://srx.sros/schema/package/v2">
  <package_meta>
    <package_id status="optional" kind="placeholder"/>
    <release_id status="optional" kind="placeholder"/>
    <timestamp status="optional" kind="placeholder"/>
    <compiler_version>OSS-Apex-1.0.0</compiler_version>
    <tenant_id>SROS</tenant_id>
    <operator_id>Skrikx Kyōten</operator_id>
  </package_meta>

  <replay_capsule>
    <raw_chat_hash status="optional" kind="placeholder"/>
    <normalized_intent>BUILD_ENTERPRISE_AI_AGENCY_WEBSITE_10_PAGE_PLATXP_USA_COBALT</normalized_intent>
    <policy_bundle_id>OSS_APEX_DEFAULT_V1</policy_bundle_id>
  </replay_capsule>

  <adapter_selection_receipt>
    <selected_adapters>
      <adapter id="adapter.text.normalize.v1" status="active"/>
    </selected_adapters>
  </adapter_selection_receipt>

  <model_routing_receipt>
    <route stage="normalize" target="small"/>
    <route stage="forge_ast" target="quality"/>
    <route stage="render" target="quality"/>
  </model_routing_receipt>

  <mirroros_receipt>
    <active_lenses>
      <lens id="LENS.SOVEREIGN.V1"/>
      <lens id="LENS.DETERMINISM.V1"/>
    </active_lenses>
  </mirroros_receipt>

  <governance_receipt>
    <classification>GENERAL_BUILD</classification>
    <decision>ALLOW</decision>
  </governance_receipt>

  <sr8_prompts>
    <active>
      <![CDATA[
<sr8_prompt id="SR8P.OSS.Active.v1" version="1.0.0" xmlns="https://sr8.sros/schema/prompt/v1">
  <role>SR8 Build Prompt</role>
  <objective>Produce a 10-page website blueprint with sitemap, design tokens, and copy brief.</objective>
  <acceptance_tests>
    <test id="T1">Sitemap has exactly 10 pages.</test>
    <test id="T2">Stack is SvelteKit + Tailwind + Motion One.</test>
  </acceptance_tests>
</sr8_prompt>
      ]]>
    </active>
  </sr8_prompts>

  <compiler_run_report>
    <governance_decision>ALLOW</governance_decision>
    <active_sr8_prompt_id>SR8P.OSS.Active.v1</active_sr8_prompt_id>
    <promotion_result>PROMOTED_TO_ACTIVE</promotion_result>
  </compiler_run_report>
</promptunit_package>
