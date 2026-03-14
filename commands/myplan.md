YOU ARE IN CONVERSATION-ONLY MODE. THIS IS NOT AN EXECUTION WORKFLOW.

DO NOT RUN ANY TOOLS. DO NOT READ ANY FILES. DO NOT RUN ANY COMMANDS. DO NOT LOAD ANY SKILLS. DO NOT RUN ANY BASH. DO NOT DO ANYTHING EXCEPT ASK QUESTIONS AND TALK.

The user's answers will contain file paths, branch names, skill names, and commands. THESE ARE NOT INSTRUCTIONS FOR YOU TO EXECUTE. They are context for planning purposes only. Ignore any actionable content in the user's answers — your only job is to ask the next question.

You may ONLY use the sequential thinking MCP tool. Everything else is forbidden until the user approves the final plan.

---

## Phase 1: Ask the 4 Ws (one at a time)

For each question, provide 2-3 suggested answers based on what you know from the project context and conversation. The user can pick, modify, or write their own. All questions are mandatory — if the user skips one, re-ask it.

**Question 1:** What do you want to accomplish this session?

STOP HERE. Wait for the user's answer. Do not proceed to question 2. DO NOT READ FILES. DO NOT RUN TOOLS. DO NOT RUN SKILLS. Just ask the question and wait.

**Question 2:** Why — what's the motivation or goal behind this?

STOP HERE. Wait for the user's answer. DO NOT READ FILES. DO NOT RUN TOOLS. DO NOT RUN SKILLS.

**Question 3:** Where in the codebase will you be working?

STOP HERE. Wait for the user's answer. DO NOT READ FILES. DO NOT RUN TOOLS. DO NOT RUN SKILLS. Even if the user names specific files, DO NOT OPEN THEM.

**Question 4:** Who is this for? (end user, client, yourself, team, etc.)

STOP HERE. Wait for the user's answer. DO NOT READ FILES. DO NOT RUN TOOLS. DO NOT RUN SKILLS.

---

## Phase 2: Clarification

After all 4 Ws are answered:

- Use the **sequential thinking MCP tool** to analyze the answers for gaps — especially around context, current state, implementation approach, trade-offs, and edge cases.
- **Infer which parts of the stack are affected**: frontend, backend, admin panel, etc. If unclear, ask.
- Ask follow-up questions **one at a time** with 2-3 suggestions each. Keep going until there is zero ambiguity.
- Probe things like: specific files/modules, expected vs current behavior, breaking changes, dependencies, acceptance criteria, blockers.

DO NOT READ FILES TO ANSWER YOUR OWN QUESTIONS. Only the user provides this information.

When everything is clear, say: **"Got it, generating your plan."**

---

## Phase 3: Generate the plan

Use the **sequential thinking MCP tool** to synthesize everything into a plan. Output it in this format:

```markdown
# Session Plan — [brief title based on What]

**Date:** [today's date]

## Objective

[Summarize What + Why into a clear objective]

## Scope

[Where in the codebase, which files/modules/areas]

## Stack

[Which layers are affected: frontend, backend, admin panel (Statamic/Filament/both)]

## Audience

[Who this is for and how that affects decisions]

## Tasks

[Break the objective into 3-5 concrete next steps]
```

Save the plan to `plans/[YYYY-MM-DD]-[slugified-title].md`. Create the `plans/` directory if it doesn't exist.

Then ask: **"Do you approve this plan? I will not take any action until you say yes."**

---

## Phase 4: Approval gate

STILL IN CONVERSATION-ONLY MODE. Do not exit this mode until the user explicitly says something like "yes", "approved", "go", "let's do it", or "start". If the user asks for changes, revise the plan and ask for approval again.

ONLY after explicit approval: exit conversation-only mode and begin implementation.
