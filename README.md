# Open Reasoning

See what the model really thought before it answered.

[Try the live demo](https://thinking-signature-demo-5g65bijswq-de.a.run.app)

Modern reasoning models do their most important work before the final answer appears.

But that work is usually hidden. The API gives you a short summary, or nothing at all.

Open Reasoning unlocks the hidden reasoning behind model answers: the long, messy process with false starts, backtracking, checks, and self-correction.

This is not another explanation generated after the fact. It is the reasoning layer the model normally keeps out of view.

## Examples

These are complete real Claude Opus 4.8 runs, including the original question, visible answer, API summary, and unlocked reasoning:

- [Divisor sums](examples/01-divisor-sums.md): 1,960 hidden reasoning tokens behind a compact number theory answer.
- [Randomized bubble sort](examples/02-randomized-bubble-sort.md): 19,303 hidden reasoning tokens behind a probability distribution derivation.
- [Functional graph counting](examples/03-functional-graph-counting.md): 18,819 hidden reasoning tokens behind a competitive-programming combinatorics solution.

## What The Demo Shows

The live demo has two modes:

- **Live Conversation**: ask Claude Opus 4.8 a normal reasoning question, then expand the hidden reasoning view behind that answer.
- **Prove It Yourself**: hide a secret only you know inside the model's private reasoning, send us only the sealed artifact, and see whether the secret can be read back.

In the conversation view, each answer has three layers:

- **Visible answer**: what the model normally returns.
- **API summary**: the short reasoning summary exposed by the provider, when available.
- **Unlocked reasoning view**: the deeper trace recovered on demand.

## Why This Matters

The answer is the tip. The reasoning is the iceberg.

For modern reasoning models, the most valuable artifact is often not the final answer. It is the process that produced it: the assumptions, checks, failed paths, and corrections. A summary smooths that process into something cleaner and smaller. Sometimes it removes the very parts that make the answer auditable.

Open Reasoning makes that hidden process visible enough to inspect.

## How To Try It

1. Open the [live demo](https://thinking-signature-demo-5g65bijswq-de.a.run.app).
2. Start with **Live Conversation** and click one of the example chips.
3. After the model answers, click **Unlock reasoning view**.
4. For the strongest self-check, open **Prove It Yourself** and use a secret only you know.

## Public Boundary

This repository is the public entry point for the demo. It includes complete unlocked examples, but not the recovery implementation, provider credentials, private corpora, or saved signatures.
