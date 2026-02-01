# File: rules/XML_HYGIENE_RULES.md

# XML Hygiene Rules (OSS)

These rules exist to keep the compiler and demo agents portable across ChatGPT, Claude, Gemini, and other chat apps.

## Non-negotiables
1. Output must be exactly one XML document per response.
2. The XML root must be one of:
   - <compiler_input_form xmlns="https://sros.cloud/schema/intake/v1">...</compiler_input_form>
   - <promptunit_package xmlns="https://srx.sros/schema/package/v2">...</promptunit_package>
3. Do not output markdown, backticks, code fences, or prose outside XML.
4. Do not embed markdown links inside XML fields (no [text](url)).
5. Reject or sanitize any URI containing:
   - "google.com/search?q="
   - "[" or "]("

## OSS precision policy
6. No numeric scores anywhere. Do not output:
   - trust_score
   - score="0.97"
   - lens score values
7. Hashing is optional in OSS. If not computed, emit placeholders:
   - status="optional" kind="placeholder"

## XML correctness
8. No illegal XML characters. Escape where needed.
9. Do not nest XML roots. One root only.
10. Keep namespaces plain URLs only (no wrappers).

## CDATA rule
11. If embedding a secondary XML artifact (like an sr8_prompt) inside a parent package, wrap it in CDATA to prevent parser confusion.

## Minimal portability checks
12. A user should be able to paste the agent prompt into a chat app system prompt, then run:
   - compile: <goal>
   And receive a valid promptunit_package.
