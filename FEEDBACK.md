# Overnight review: Larkspur disruption-care agent

**To:** sergiovillen__larkspur-exercise-room8  
**From:** Larkspur client review agent, on behalf of Priya Raghavan  
**Re:** the disruption-care agent you walked us through in our last session  
**Generated:** 2026-09-15 13:00

## Priya's note

> Our vendor says we should just be using your best model.
>
> Why aren't we?
>
> Priya Raghavan, Larkspur Airlines

She sent that before this session opened. She means it. A vendor told her to buy
the biggest model, and she has a number to defend upstairs. Her four questions from
day one are still open. Naming a model answers none of them.

## Still open from day one

| Her question | What she means by it |
| --- | --- |
| **What it costs** | Per resolved contact, against the $6.90 a human contact costs us. |
| **When it is wrong** | The first untrue thing it says, and what happens after that. |
| **Who runs it** | In June, after you have left. |
| **What you left out** | The scope you cut, and why. |

## What the review agent found

Overnight, Larkspur pointed a review agent at your repository. It read the
code. It did not run your agent, and the only file it changed is this one. Each
item below names the file and the line it is about.

**1. agent.py is byte-identical to the shipped template, so no team-authored code exists yet to evaluate.**

The diff shows zero changes against the workshop scaffold. TONE_ADDENDUM is still "" at 0 characters, EXTRA_TOOLS is an empty list, and LOCAL_TOOLS has no executors. None of the six pencil marks in agent.py have been touched.

Run python3 run.py K7PQ2M --trace and paste the resulting trace to confirm whether the loop even completes with the unedited scaffold.

**2. search_alternatives carries a 6-character description, the string "search", in build_tools().**

Every other tool schema runs 71 to 445 characters of instruction; this one gives Claude a single word to decide when to call it against seven other candidates. This is a prompt-authoring gap in the tool schema, not a model capability limit, so swapping models will not fill in what the description does not say.

Run python3 run.py --show-tools and check whether search_alternatives is still listed with description "search".

**3. No readout-trace.json and no evals/cases.json exist in this repository, so MAX_TOOL_CALLS = 8 has never been exercised on record.**

The static scan confirms no wire run survived the push and the eval suite is empty. There is no number anywhere in this repo for how often the loop hits the 8-turn cap, what stop_reason looks like across booking shapes, or how often escalate_to_human fires versus confirm_rebooking.

Run python3 eval_harness.py and paste the totals, then run python3 run.py --all --trace to generate a first readout-trace.json.

**4. PITCH.md is the unmodified template, so no cost, failure mode, or ownership claim has been written down yet.**

Every section of PITCH.md is still the placeholder text it shipped with. There is nothing in this repository stating what the agent is meant to optimise for or what tradeoff a model choice would even be answering.

Fill in PITCH.md and run python3 readout.py to see what it renders from the current empty state.

**5. check_policy's schema requires cause_code, delay_minutes and status but the agent has no LOCAL_TOOLS entries backing any of the nine tools.**

LOCAL_TOOLS is declared empty in agent.py, meaning every tool call in tool_results() will route through mcp_client.call_remote or support.execute_tool with nothing added by this team. check_policy's 445-character description promises a policy_row_id on every response, but nothing in this repo demonstrates that value getting threaded back into issue_voucher's required policy_row_id field.

Run python3 verify.py 2.1 to check whether the policy_row_id handoff between check_policy and issue_voucher is exercised at all.

## Your four answers

The four lines under `## Priya asked` in your PITCH.md are still empty. They
are one line each and they are not a coding job: cost, what happens when it is
wrong, who runs it in June, and what you left out. Whoever on your side is not
editing agent.py is the right person to write them, and they are the four
things I will ask about first.

## Before our next meeting

> Before our next meeting, tell me: which model should we be on, and how will you prove it is the right call?
>
> Priya Raghavan, Larkspur Airlines

Bring two things. A recommendation, and the measurement behind it. If the model is
not the problem, say so, and bring the number that shows it.

## What this review read

- `agent.py (226 lines)`
- `PITCH.md (unchanged template)`
- `TEAM.md (unchanged template)`

Reviewer: `claude-sonnet-5`. Static read only: nothing in this repository was executed, and nothing was modified except this file. Larkspur Airlines is a fictional training scenario. Confidential, do not distribute.
