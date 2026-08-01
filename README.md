# hypershot-protocol

*The art of priming structure without priming content.*

[![license](https://img.shields.io/badge/license-CC_BY_4.0-3b7ddd)](LICENSE.md)
![lineage](https://img.shields.io/badge/lineage-Lexideck_curriculum-9b8cf7)

A Claude Code skill for the moment you would otherwise reach for few-shot
examples — and would contaminate the context window doing it.

> **The technique is Matthew Murphy's.** The hypershot comes from the **Lexideck
> Prompt Engineering Curriculum** by
> **[Matthew Murphy](https://github.com/gusthemole)**, as does the idea that a
> variable's *name* can carry its own generation rule. This repository ships the
> deployed artifact; the curriculum is the canonical authority.
>
> Full curriculum: [patreon.com/c/LexideckTechnologies](https://www.patreon.com/c/LexideckTechnologies)

## The problem it solves

Few-shot prompting contaminates by construction. Show a model "the answer to 2+2
is 4" and it picks up an arithmetic prior even when the real task is a poem — the
example's *content* leaks into the response distribution.

A hypershot gives a **frame** instead: a structural skeleton with **free
variables** where the examples would be.

```md
User: "{Greeting_Input}" -> AI: "{Warm_Professional_Response}"
```

One zero-semantic frame implicitly enumerates every valid instantiation, so the
model inhabits the equivalence class directly instead of interpolating between
scattered sample points.

## The continuum

Each variable sits somewhere on a dial, and a single frame mixes settings freely:

| setting | form | carries |
|---|---|---|
| **spread** | `...` | pure structural slot, no type, no instruction |
| **categoric** | `{Greeting_Input}` | an abstract type, no behaviour |
| **instruction-bearing** | `{Concise_Reply_With_No_Fluff}` | type and generation rule in one token-position |

**Which setting depends on how much load the frame already carries.** Use the
lightest variable that does the job.

## Why it works

**Primacy.** What sits earliest in context sets the strongest prior for
everything after. A hypershot placed before generation seeds the desired shape
*before any output begins*, so the patterns you are designing out never become
live options — the basin of attraction is already set.

That also tells you where concrete examples may live: **invariants at the system
layer, variant content downstream.** The test is one question — *across a hundred
invocations, will this exact token appear identically in all hundred?*

## Install

```bash
git clone https://github.com/OpenCnid/hypershot-protocol.git
cp -r hypershot-protocol ~/.claude/skills/hypershot-protocol
```

Or install it with the rest of the stack:
[OpenCnid/dovetail](https://github.com/OpenCnid/dovetail).

Pairs with [OpenCnid/prompt-engineering](https://github.com/OpenCnid/prompt-engineering),
whose master template is a hypershot.

## License

Prose and skill: [CC BY 4.0](LICENSE.md) © OpenCnid Labs. The technique is
Matthew Murphy's — credit the source, not just the application.
