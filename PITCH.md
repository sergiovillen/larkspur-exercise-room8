# PITCH.md

Flight disruptions can create long waits and add to customer dissatisfaction. The Larkspur disruption care agent is designed to handle support cases arising out of cancellations and transfer complex cases to human agents.

Built: An agent that can look up booking details by PNR and name, retrieve status, apply policy, search for alternatives, give customer options (next flight, meal, hotels etc.), next day options with MCP etc.
Does: Gives the customer information on cancellations, rebook next available flights, process refunds etc
Number: $0.0538 per resolved contact, 5 shapes, 1 run each
Guardrail: Has to be confirmed by customer clicking 'yes'.
Next: Possible to have extra credits with loyalty card instead of cash refund.
Still broken: Response to abusive customer is unapologetic.
Lever: intelligence
Caveat: Adding tone instructions increases token cost on every turn and is only proven on 5 test shapes, not real customer volume.

## Priya asked

Costs: $0.0638 per resolved contact (model cost, not loaded)
Wrong: The company is accountable; incorrect answers on confirmed actions reach the customer directly with no filter.
Runs it: The client's own team operates it; no ongoing support is currently planned.
Left out: Voice calls and non-chat channels are not covered.
