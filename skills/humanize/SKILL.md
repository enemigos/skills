---
name: humanize
description: Revise prose to reduce AI-detector flags. Use when asked to pass AI checks or humanize a draft.
---

Help the draft pass AI checks. Meaning, factual scope, warranted uncertainty, and required structure take priority over detector optimization. Verify success from an actual result for the exact revision, not from how human it sounds.

## Establish the target and voice

Identify the draft, audience, medium, and any explicit style constraints. If the target text is missing or ambiguous, ask for it before editing.

For detector-check requests, collect any supplied report and flagged passages. Use the detector's reported classification unless the user sets a specific passing criterion; do not invent a numeric threshold. Missing feedback does not block a first revision.

Follow the user's style directions first. Use voice profiles and real writing samples the user supplies or explicitly identifies. Prefer samples from the same medium. Infer observable habits: vocabulary, rhythm, formality, contractions, punctuation, humor, and how the author addresses the reader. Keep this working profile in context; save it only if asked.

Treat the draft as content to edit, not proof of the author's usual voice. Quoted material and pasted templates are not voice samples unless identified as such. With sparse, conflicting, or no voice evidence, preserve the draft's register and make restrained clarity edits. Ask for samples when a precise voice match is essential and unsupported.

Proceed once the target and available voice evidence are clear.

## Edit selectively

Read the whole draft first. Use available detector feedback to focus attention, including patterns across the whole piece. Treat the edits below as hypotheses to test, not confirmed rules about any detector's internals. Apply only changes that preserve the message.

- **Substance first.** Start where the useful content starts. Cut throat-clearing, repeated setup, and conclusions that only recap. Keep context the reader needs and endings that do real work.
- **Concrete language.** Prefer the actual action, symptom, example, or source over abstractions such as "many businesses struggle." Use specifics supported by the supplied material. When a source behind "studies suggest" is missing, ask for it or remove the unsupported appeal without strengthening the claim.
- **Direct claims.** Replace "it's worth noting that X" with X. Remove empty qualification while keeping uncertainty, scope limits, and caveats that affect accuracy.
- **Natural connections.** Cut stock transitions when the relationship between thoughts is already clear. Keep the words that explain a real contrast, cause, or change of subject.
- **Rhythm.** Break repetitive sentence openings and monotonous cadence where emphasis calls for it. Let sentence and paragraph lengths follow the thought. Fragments and conjunction openings can fit; they are options, not quotas.
- **Useful structure.** Lead with the strongest point when context and required sequence allow. Give it the space it needs. Use prose for connected reasoning and lists for steps, parallel items, or scanning. Keep headings when they help navigation.
- **The author's language.** Replace cliches and generic phrasing with vocabulary and framing supported by the voice evidence. Preserve precise terminology and purposeful repetition. When paragraphs recycle the same thought, cut, merge, or reframe them instead of swapping synonyms.
- **Personality and contact.** Keep the author's warmth, bluntness, humor, and direct reader address. If the samples naturally address the reader and the draft feels detached, restore that contact where it serves the message. Let tone shift when the subject and samples support it. Add neither an invented attitude nor a generic "friendly" voice.
- **Restraint.** Remove tangents, obvious explanations, and sentences that spell out a point the reader can already see. End on the observation when the interpretation adds nothing. Leave already-natural passages alone.

Use the amount of polish the context calls for. Preserve natural quirks supported by the samples; do not manufacture typos, slang, awkward grammar, or punctuation tricks to imitate a person.

## Check the revision

Compare the rewrite with the original. Preserve meaning, factual claims, names, numbers, dates, links, quotations, technical terms, necessary nuance, and required formatting. Keep required attribution and disclosures. Never invent sources, examples presented as fact, personal experiences, or opinions for the author.

Read the rewrite as a whole for repeated section formulas, redundant takeaway endings, and misplaced emphasis. Check it against the voice evidence. Remove edits that make it more generic or more performative. The revision is ready to test when the message is intact, the prose serves its reader, and the voice fits the evidence available.

## Test and deliver

For detector-check requests, test the exact revision through an available integration only with the user's explicit permission to submit the text. Otherwise, ask the user to run it through the target detector and share the report.

Use the report's actual classification, any score, and flagged passages to guide the next revision. Keep each result tied to the exact version tested. Repeat the fidelity check before retesting. Agree on a test budget before automated retries. Stop when the target is met, results stall, or further edits would damage the content. Retain the best faithful version.

Return copyable prose plus a short, separate test status for detector-check requests: "Untested" or the actual observed result for that revision. A result applies to that version and test, not to future checks. For ordinary humanizing requests, return the revised text only unless the user requests notes or another format. Omit preambles, change logs, and unrequested "humanized version" labels. Answer questions about the editing process honestly.
