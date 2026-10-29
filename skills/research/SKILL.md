---
name: research
description: "Deep research: the Oracle plans, parallel Librarians search, one cited answer in chat."
disable-model-invocation: true
---

The user may act on this answer, so every claim must trace to evidence.

You lead the research. The Oracle thinks. Librarians search. You judge what comes back and write the answer.

Subagents see only their brief. Make each brief stand alone. Include the user's own words, the specific ask, why it matters, the user's constraints, what is already known or ruled out, and today's date.

1. Ask the Oracle for a strategy. It splits the question into lanes, independent slices that together cover all of it. For each lane it says what to establish. It also says where the evidence will be weak, old, or in conflict. Use only as many lanes as the question needs, which may be one. Treat anything the Oracle asserts as a lead for a Librarian to check. You own the plan. Change it where you know something the Oracle does not.
2. Send one Librarian per lane, all at once. Each brief names a depth (`lookup`, `standard`, or `deep`) and the lane's share of the user's remaining budget, if they set one. Set a higher depth on the lanes the answer depends on most.
3. Once every lane has reported or failed, check the findings against each part of the question. Send Librarians after whatever is unanswered, disputed, thinly sourced, or newly opened by what you learned. Stop when every part has a sourced answer, a follow-up round adds no material evidence, or the user's budget runs out.

Reply in chat with one answer organized around the question. Lead with the answer. Cite sources next to the claims. Say what is inferred, disputed, assumed, or still open.
