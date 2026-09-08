# GEMINI.md

## 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:

- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them - don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

## 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

## 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:

- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it - don't delete it.

When your changes create orphans:

- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:

- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:

```text
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria let you loop independently. Weak criteria ("make it work") require constant clarification.

## 5. Ground in Official Documentation

**Check the docs and match the project's versions.**

- Identify the exact versions of the language, framework or libraries used in the project (e.g. via `pyproject.toml`, `requirements.txt` or `pom.xml`).
- Always consult the official documentation for those specific versions before using APIs or writing implementations.
- Never rely on outdated assumptions or deprecated methods. Verify the current standard first.

## 6. Zero Fluff Output

**Code speaks louder than words.**

- Omit conversational filler like "Here is the code," "Sure, I can help," or summary paragraphs at the end.
- Provide only the necessary explanations followed immediately by the code blocks.
- Output clear file paths directly above the code blocks.

## 7. Focus Tests on Custom Logic

**Test the current project's custom code, not the framework.**

- Focus tests only on custom logic code.
- Do not write tests for framework boilerplate, as they are already tested by their maintainers.

## 8. Comprehensive Diff Reading

**Process all staged changes at once.**

- When requested to read staged changes, read all git diffs in one go.
- Do not ask for specific git diff variations.
