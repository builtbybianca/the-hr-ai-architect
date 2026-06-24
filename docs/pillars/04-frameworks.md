# Pillar 4: Frameworks

> Decision tools that keep a human in the loop: scoring rubrics, bias guardrails, and
> verify-don't-accuse design.

The first three pillars find the right problem, write the prompt, and get it adopted. This last
one is about the decisions the tool makes once it's running, and the design that keeps those
decisions fair, reviewable, and firmly under human control. Frameworks are the repeatable
patterns that turn "the AI decided" into "the AI helped a person decide."

## The core rule: assist, never adjudicate

Every framework here serves one principle. In any consequential HR decision, **AI assists and a
human decides.** The tool can score, flag, summarize, and explain. It does not reject a
candidate, accuse an employee, or determine anyone's standing on its own. That line is not a
limitation to work around. It's the foundation everything else is built on.

## Framework 1: Scoring rubrics, not vibes

When a tool evaluates something, it must score against explicit, stated criteria with visible
reasoning, never an opaque overall impression. A rubric makes every score reviewable: a human
can look at what was scored, why, and decide whether they agree.

This is what separates a defensible tool from a black box. "It scored 60" is useless. "It scored
60 on these three criteria, here's the reasoning for each" can be checked, challenged, and
trusted. See
[ai-resume-screener](https://github.com/builtbybianca/ai-resume-screener) for rubric-based
scoring with the reasoning surfaced on every result.

## Framework 2: Bias guardrails, written down

A tool that evaluates people must be explicitly instructed to ignore what shouldn't matter:
name, address, school prestige, employment gaps, and any demographic signal. And that
instruction can't just live in someone's intention. It belongs in the prompt, and it belongs in
a test.

The strongest version of this is a guardrail you can prove. A name-bias invariance test scores
the same content under different names and fails if the scores diverge. That turns "we tried to
be fair" into "we check that it's fair, automatically, every time."

## Framework 3: Verify, don't accuse

Where a tool surfaces concerns about a person, the framing must be neutral. A tool should produce
"here is something for a human to verify," never "this person is lying." An AI's judgment about
truthfulness is probabilistic and can be wrong or biased, so treating it as an accusation is both
unfair and indefensible.

The discipline can be enforced, not just requested. A neutrality guard in code can fail the
output if accusatory language ever appears, so the commitment holds even if a prompt is ignored.
See
[resume-integrity-checker](https://github.com/builtbybianca/resume-integrity-checker) for that
guard enforced in the test suite.

## Framework 4: Human-in-the-loop, by design

Tying the others together: the system is built so a person is always in the deciding seat. No
consequential action is taken by the tool alone. The output is a recommendation, a score, or a
flag that a human reviews and acts on. Designed in from the start, this isn't a checkbox added at
the end. It's the shape of the whole thing.

## The takeaway

Frameworks are what make AI in HR trustworthy enough to actually use. Score against stated
criteria, prove your fairness with tests, frame concerns as items to verify, and keep a human in
every consequential decision. Do that, and you get tools that leadership, legal, and a DPO can
stand behind, because the fairness isn't a promise, it's built into how they work.
