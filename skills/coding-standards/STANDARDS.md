# Coding Standards

## HTTP APIs

Without an error schema, a caller must guess what failed. A structured error lets the caller fix the input and retry with intent.

- Each 4xx and 5xx response has a schema. 429 and 503 responses give `Retry-After` data. 400 responses identify invalid fields.
- All errors use one schema.
- Each error has a machine-readable code. Each schema has a human-readable message.
- Examples do not expose internal details.

Predictable names let callers infer paths safely. Inconsistent names force callers to memorize exceptions and can cause bugs.

- Resource paths use nouns, such as `/users` and `/orders`. Collection paths use plural names.
- All paths use one case. Prefer kebab-case.
- Use HTTP methods, not action verbs in URLs.

## Error Message Design

- Write error messages to help the reader understand and recover: say what happened, why it happened if known, what the impact is, and what to do next
- Prefer specific, concrete wording over vague or generic messages
- If the cause is unknown, say that plainly; do not invent false precision
- State what is still true or preserved, especially whether data, prior work, or system state remain intact
- Include the most useful recovery action or next diagnostic step
- Match detail to audience: user-facing errors should be plain and actionable; internal errors should include precise operational context needed for debugging
- Internal errors should name the failing operation, relevant identifiers, expected vs actual state when useful, and the most likely remediation path

## Sensitive data, telemetry, and debugging

Prefer end-to-end structured tracing across requests, jobs, workflows, application modules, adapters, and external calls.

Tracing/logging should make failures diagnosable with safe fields:

- domain IDs
- operation names
- dependency/provider names
- state tags
- retry counts
- typed error tags
- safe summaries

Do not put secrets in errors, traces, logs, or snapshots.

### Explicitness

Favor explicit, traceable code over implicit "magic". A reader (human or agent) should be able to follow where every name comes from without running tooling.

## Write better error messages

Treat errors as recovery flows. Design them with product, design, and engineering alongside happy paths.

Before writing, inspect the trigger and UI. Verify what failed, what succeeded or stayed safe, the known cause, placement, whether it blocks the task, and supported recovery paths. Flag missing facts or recovery options as product or engineering gaps. Never invent causes, guarantees, or actions.

Use only the parts the situation needs:

1. **Outcome:** State what happened in user terms, including partial success.
2. **Cause:** Explain the known reason plainly. Own failures on our side.
3. **Reassurance:** Say what was saved or unchanged only when verified.
4. **Action:** Give an exact recovery step. Say where or how when needed.
5. **Escape:** Offer another path or support if the user may remain blocked.

Keep copy calm, concise, and empathetic. Do not blame users or third parties. Remove unnecessary jargon and excessive apologies. Avoid jokes or cute language when money, access, work, data, or trust is at risk. Use descriptive help links, not "Learn more." Specific messages must still be understandable and actionable.

Challenge generic messages. Use a fallback only when the cause is unknown, with a next step or exit. Instrument errors, review them one month after launch, and keep improving them.

Prioritize frequent or blocking errors. Track triggers, affected state, frequency, owners, fixes, and follow-up dates. Review copy and implemented behavior together.

## Comments

Avoid code comments at all cost unless it's for JSDocs / Library documentation, a required runtime, compiler, or linter directive, or a runtime indicator such as `// @env node`.
