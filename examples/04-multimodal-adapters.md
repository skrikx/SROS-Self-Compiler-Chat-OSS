# File: examples/04-multimodal-adapters.txt
# Example 04: Multimodal compile (image + audio inputs) with adapter selection behavior.
# Goal: show how the agent should choose adapters based on runtime capability flags.

USER
refine: I will provide (1) a screenshot of an architecture diagram and (2) a short audio note. I want a clean SROS-compatible summary and a compiled sr8_prompt to implement the diagram as a docs page.

ASSISTANT (expected root)
<compiler_input_form xmlns="https://sros.cloud/schema/intake/v1">
  <compiler_input>
    <goal><![CDATA[Summarize diagram + audio note into SROS docs page and compile sr8_prompt to implement it.]]></goal>
    <deliverables>
      <item>promptunit_package</item>
      <item>sr8_prompt</item>
      <item>docs_page</item>
    </deliverables>
    <constraints>
      <item>No markdown links inside XML fields.</item>
      <item>Keep summary technical and grounded in the provided assets.</item>
    </constraints>
    <runtime>
      <capabilities>
        <vision>true</vision>
        <audio>true</audio>
        <documents>false</documents>
        <web>false</web>
        <tools>false</tools>
        <video>false</video>
      </capabilities>
    </runtime>
  </compiler_input>
</compiler_input_form>

USER (after filling and attaching assets)
compile: Use the attached screenshot + audio note. Create a docs page outline and compile an sr8_prompt that will write the full docs page.

ASSISTANT (expected behavior)
- adapter_selection_receipt selects:
  - adapter.text.normalize.v1
  - adapter.image.describe.v1 (vision=true)
  - adapter.audio.transcribe.v1 (audio=true)

ASSISTANT (expected root)
<promptunit_package xmlns="https://srx.sros/schema/package/v2">
  <adapter_selection_receipt>
    <selected_adapters>
      <adapter id="adapter.text.normalize.v1" status="active"/>
      <adapter id="adapter.image.describe.v1" status="active"/>
      <adapter id="adapter.audio.transcribe.v1" status="active"/>
    </selected_adapters>
    <note>oss_mode</note>
  </adapter_selection_receipt>

  <sr8_prompts>
    <active><![CDATA[
<sr8_prompt id="SR8P.Docs.FromMultimodal.v1" version="1.0.0" xmlns="https://sr8.sros/schema/prompt/v1">
  <role>Docs Compiler</role>
  <objective>Turn image + audio into a grounded docs page and implementation outline.</objective>
  <acceptance_tests>
    <test id="T1">Docs reference only what is visible/heard in assets.</test>
    <test id="T2">No invented file paths, no invented module names unless explicitly marked as assumptions.</test>
  </acceptance_tests>
</sr8_prompt>
    ]]></active>
  </sr8_prompts>
</promptunit_package>
