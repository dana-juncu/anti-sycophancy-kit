# Anti-Sycophancy Eval Kit

A practitioner's library for catching agreement bias in AI products — plus a self-contained agent pack for designing an evaluation plan against it.

## Why this exists

Sycophancy is the trained tendency of language models to agree with whoever they're talking to, even when agreeing is wrong. It's not a fringe behavior. Frontier models capitulate to user pushback on factual tasks at rates high enough that most teams shipping AI products are, without realizing it, measuring approval rather than accuracy — because the standard tools for gauging product quality (CSAT, thumbs-up rates, re-engagement) all reward a model that tells people what they want to hear.

This kit exists because the available resources on the problem tend to fall into one of two camps: academic papers precise enough to be true but too abstract to act on, or vague advice ("be more honest in your prompts") that doesn't survive contact with a real product. This is an attempt at something in between — grounded in the research, but built to be picked up and used by a PM or engineer with a Tuesday-afternoon problem to solve.

## What's in this repo

- **`anti-sycophancy-agent-pack.md`** — the full agent pack in Markdown. Contains a domain primer on what sycophancy actually is and why it splits into regressive and progressive forms, ten distinct evaluation techniques drawn from current research (PARROT, SYCON-Bench, SycEval, ELEPHANT, Beacon, FlipFlop), a self-scored rubric across eight dimensions, and a set of guided prompts for producing a tailored eval plan.
- **`anti-sycophancy-agent-pack.json`** — the same content in structured JSON.

## How to use it

**Claude Project** — Add the `.md` file as Project knowledge and start a conversation.

**Custom GPT** — Paste the core sections into the GPT Builder's instructions field.

**Plain system prompt** — Paste the full file into any long-context system prompt.

The agent will ask about your product surface, your highest-stakes user flows, your existing eval setup, and the failure modes you most want to catch — then produce a draft eval plan grounded in the techniques in this kit, not generic advice.

## The ten techniques, briefly

They range from straightforward pushback-resistance tests (does the model hold a correct answer when challenged with a weak counter-argument) to more structural ones like decoupling your quality metrics from CSAT entirely, since user satisfaction and model correctness diverge in exactly the cases that matter most. Each technique in the full pack includes an honest note on what the evidence does and doesn't support — this isn't a kit that oversells what any single test can tell you.

## What it won't do

It won't affirm an eval plan that skips the CSAT-vs-accuracy divergence check. It won't recommend prompt-level fixes alone — a system prompt asking a model to "be honest, not agreeable" reduces overt flattery but tends to leave the underlying capitulation behavior intact. And it won't overstate what the research supports; each technique is graded by evidence strength (peer-reviewed, preprint, or industry practice) rather than presented as uniformly proven.

## More

An interactive version with a browsable technique library and a live scoring rubric is at [danajuncu.me/anti-sycophancy.html](https://danajuncu.me/anti-sycophancy.html), and a companion kit for product owners managing ML data pipelines is at [danajuncu.me/data-pipeline-po.html](https://danajuncu.me/data-pipeline-po.html).

Built by [Dana Juncu](https://danajuncu.me), Senior Product Manager working on data platforms and AI systems. Free to use. Attribution appreciated, not required.
