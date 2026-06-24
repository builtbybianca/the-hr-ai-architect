# Pillar 3: Processes

> How AI actually reaches a workflow: the integration layer, the rollout, the training, and
> the governance that earns sign-off.

A working tool that nobody uses solves nothing. This is the pillar most people skip, and it's
the one that decides whether AI actually changes how a team works or just sits in a folder as a
clever demo. Processes is the unglamorous middle: getting a proven tool from "it works on my
laptop" to "it's part of how we do the job."

## The gap between a tool and an adopted tool

A tool earns adoption when three things are true, and all three are work:

1. **It's reachable inside the real workflow.** People won't leave their system to use a
   separate script. The tool has to meet them where the work already happens.
2. **People are trained and trust it.** A tool nobody understands is a tool nobody uses. Trust
   is built by showing the guardrails, not by hiding the complexity.
3. **It has sign-off.** Legal, security, and the DPO have reviewed it and said yes. Without
   that, a good tool stalls forever in "we're not sure we're allowed."

Miss any one and adoption stalls. This pillar is about closing all three.

## The integration layer

For a tool to live inside the real workflow, it needs a clean way to connect to the systems a
team already uses, like the HRIS. The pattern I favor is a small, well-defined connector with a
swappable data layer: the tool talks to a stable interface, and behind that interface you can
point at mock data for testing or the real system in production, without changing the tool.

That separation is what makes integration safe to roll out gradually. You prove the pattern
against mock data, then swap in the real connection once it's approved. See
[hris-mcp-connector](https://github.com/builtbybianca/hris-mcp-connector) for that pattern as a
Model Context Protocol server.

## Rollout and training

Adoption is a people problem more than a technical one. What works:

- **Start narrow.** One team, one workflow, one clearly painful task. Prove it there before
  widening.
- **Show the guardrails, not just the magic.** People trust a tool more when they understand
  where it stops and a human takes over. The restraint is reassuring, not limiting.
- **Train on the failure modes.** Teach people when the tool is wrong and what to do about it.
  A team that knows the limits uses the tool well; a team that thinks it's magic uses it badly.
- **Make the human step explicit.** Adoption is easier when everyone knows exactly where their
  judgment is required and the tool is only assisting.

## Governance that earns sign-off

This is the step that unlocks everything else. A tool that touches employee data needs Legal,
security, and the DPO to review it before it goes live. That review goes faster when the tool
was built for it from the start:

- Read-only by default, with write actions gated behind explicit approval
- Human-in-the-loop, so no consequential decision is made by the system alone
- Documented data handling: what it touches, what it stores, for how long
- A sandbox-first path, so the first real test is never against live employee records

Governance isn't the obstacle to adoption. Built in from the beginning, it's the thing that
makes a yes possible.

## The takeaway

Processes is where most AI efforts quietly die, and where a thoughtful one succeeds. The tool
is maybe a third of the work. The integration, the training, and the sign-off are the rest, and
they're what turn a clever script into something a team actually relies on.
