# Pillar 2: Prompts

> Production-tested prompt patterns for real HR workflows, with guardrails written into the
> prompt rather than hoped for.

Once you know which pains are worth solving, prompts are where the work actually happens. But
a prompt that works once in a demo is not the same as a prompt a team can rely on every day.
This pillar is about the difference: the structure that makes a prompt repeatable, safe, and
good enough to hand to someone else.

## A prompt is a spec, not a wish

The most common mistake is treating a prompt like a polite request and hoping for the best.
A reliable prompt reads more like a specification. Every prompt in my work follows the same
four-part structure:

1. **Role and context first.** Tell the model who it is and what it knows before asking for
   anything. "You are an HR communications specialist" produces different, better output than
   a cold request.
2. **Explicit output format.** Specify the structure. A table, a numbered list, a JSON object.
   Never leave the shape to chance, because inconsistent shape is what breaks everything
   downstream.
3. **Guardrails inline.** State what to avoid inside the prompt itself. Don't hope the model
   avoids legal-exposure questions or breaks anonymity; tell it not to, explicitly.
4. **Variables in brackets.** Use placeholders like `[JOB_TITLE]` and `[POLICY_NAME]` so one
   well-built prompt becomes reusable across every case, by anyone on the team.

## The guardrail principle

The single most important habit: **the guardrail goes in the prompt, not in your hopes.**

If a survey-analysis prompt must protect anonymity, the instruction "paraphrase, never quote
verbatim" lives in the prompt. If a policy summarizer must not invent rules, the instruction
"flag anything ambiguous with [NEEDS HR REVIEW] rather than guessing" lives in the prompt. The
flag is not decoration. It is the line that stops a confident wrong answer from reaching an
employee.

This is the same discipline as human-in-the-loop design, pushed down to the prompt level:
build the safety into the instruction, so it holds even when no one is watching the output
closely.

## Why a library beats a clever one-off

A single brilliant prompt helps one person once. A **library** of tested prompts, organized by
workflow, changes how a whole team works. The difference is in the boring parts:

- Each prompt is **tested by more than one person** on realistic inputs before it's trusted.
- Each prompt documents its **failure mode** — the "notes from real use" that tell the next
  person when it breaks and how to avoid that.
- Each prompt passes a **governance review** before rollout, so Legal and the DPO can sign off
  on the whole library rather than auditing prompts one at a time.

See [hr-ai-prompt-library](https://github.com/builtbybianca/hr-ai-prompt-library) for the
structure and a governance review checklist.

## The takeaway

Good prompting in an HR setting isn't about clever wording. It's about structure, explicit
guardrails, and the discipline to test and document before you trust. A prompt you'd stake an
employee's experience on looks a lot more like engineering than like writing.
