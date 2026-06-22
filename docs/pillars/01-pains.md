# Pillar 1: Pains

> Start from the HR problems AI can actually solve, and be honest about the ones it can't.

Most AI adoption fails before a line of code is written, because it starts from the wrong
question. "How do we use AI?" is the wrong question. "Which of our real, recurring,
expensive problems is AI actually good at?" is the right one. This pillar is about finding
those, and being just as clear about where AI doesn't belong.

## The test for a real pain

Before a problem is worth solving with AI, it should pass three checks:

1. **It recurs.** A one-off annoyance isn't worth automating. The problems worth solving
   happen weekly, monthly, every onboarding, every hiring round.
2. **It's expensive.** In hours, in risk, or in mistakes. If it's cheap to do by hand, leave
   it alone.
3. **It has a clear right answer, or a clear "needs a human" answer.** AI is strong where
   the task is bounded and reviewable. It is dangerous where the answer is a judgment call
   with real consequences and no review step.

If a problem fails any of these, it's probably not where AI should go first.

## A real pain, worked through: document fraud in onboarding

Remote-first hiring means identity documents arrive digitally, and manipulated documents are
cheap to produce. Between "document received" and "document accepted," most HR teams have no
technical screening at all. The pain recurs (every hire), it's expensive (the risk is real),
and it has a clear "needs a human" answer (flag for review, never auto-reject).

That made it a good fit. The result was a metadata analysis pipeline that flags signs of
manipulation for human review, never a verdict. See
[hr-idv-fraud-detection](https://github.com/builtbybianca/hr-idv-fraud-detection) for the
build and the honest discussion of its limits.

## The pains worth a hard look in most HR teams

- **Screening volume.** Reviewing many resumes against a role is repetitive and bounded, a
  good fit for assisted scoring with a human deciding.
- **Policy translation.** Turning dense policy into plain employee guidance recurs constantly
  and is low-risk when a human approves the output.
- **Onboarding document checks.** As above: a screening layer where none existed.
- **Survey and feedback synthesis.** Theming open-text responses at volume, with anonymity
  safeguards built in.

## The pains AI should NOT own

Being honest about this is what earns trust from leadership and legal:

- **Final hiring or firing decisions.** AI can inform; it must not decide.
- **Anything that determines someone's pay, status, or standing without review.**
- **Sensitive employee-relations judgment** — investigations, accommodations, discipline.
- **Anything where a confident wrong answer causes real harm** and there's no human check.

The pattern: AI earns the bounded, reviewable, repetitive work. Humans keep the judgment
calls. Naming that line clearly, up front, is what makes the rest of an AI rollout possible.
