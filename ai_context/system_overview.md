<!--
TARGET: GenAI model.
USAGE: A highly-condensed, machine-readable summary of the system architecture for providing context to the AI.
-->

# System Architecture Summary

## Agents:
- **RootAgent (TerraMind_Coordinator)**: Orchestrates the workflow. Delegates tasks strictly.
  - Model: gemini-2.5-pro
  - Sub-agents: [GuardAgent, PlannerAgent, CoderAgent]
- **GuardAgent**: Validates user query. Scope (F1) & Capability (F6).
  - Model: gemini-1.5-flash-latest
  - Tools: [log_out_of_scope_question]
  - Delegates to: PlannerAgent
- **PlannerAgent**: Collaborates with user to create a JSON analysis plan. Handles F2, F3, F4.
  - Model: gemini-2.5-pro
  - Output: JSON plan + approval question.
- **CoderAgent**: Writes GEE Python code and estimates cost from a JSON plan. Handles F5.
  - Model: gemini-2.5-pro
  - Input: JSON plan

## Workflow:
1. User Query -> RootAgent
2. RootAgent -> GuardAgent (Validation)
3. GuardAgent -> PlannerAgent (If valid)
4. PlannerAgent <-> User (Dialogue to create JSON plan)
5. User -> RootAgent (Approval)
6. RootAgent -> CoderAgent (If approved, pass JSON plan)
7. CoderAgent -> Final Code + Cost Estimate
