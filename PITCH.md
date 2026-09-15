# PITCH.md

Six lines and a lever. Your words. The last two are scored.

Built: A disruption-care chat agent for Larkspur Airlines, wired to the Messages API with nine tools and an MCP server carrying next_available_day and fare_rules.
Does: Resolves a stranded customer's cancellation, delay, or diversion in one conversation — looks up the booking, checks live flight status, reads policy, and tells them exactly what they are owed without a human in the loop for standard cases.
Number: $0.056 per resolved contact before the tone lever, $0.057 after; 5 shapes, 3 runs each.
Guardrail: Never confirms a rebooking without a customer-issued confirmation token — proven by the irreversible eval case, which passed the hard gate with must_not_call confirm_rebooking.
Next: Add prompt caching; the schema payload is 2,879 tokens on every turn whether the tool fires or not.
Still broken: An abusive message or legal threat reaches the entitlements path without tone screening unless TONE_ADDENDUM is active — the intelligence lever closes it, but the wording is fragile.
Lever: intelligence

## Priya asked

Costs:
Wrong:
Runs it:
Left out:
