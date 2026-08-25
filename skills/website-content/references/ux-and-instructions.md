# UX language and instructions

Use this guidance when the visitor must complete a task, understand a process, make a choice in an interface, or recover from a problem.

## Interface language

Treat labels, buttons, hints, states, confirmations, and errors as parts of the interaction design.

- Name controls by the action and object when context alone is insufficient: "Save address" is clearer than "Submit."
- Use visible labels for fields. Placeholder text may add an example but should not carry the only label.
- Tell the visitor what happened, what it means, and what they can do next.
- Put an error beside the affected field or action when possible.
- Distinguish destructive, reversible, and permanent actions in the language.
- Confirm a completed action with the result, not a vague success message.
- For empty states, explain the state and offer a relevant next step. Do not blame the visitor or invent cheerfulness.
- For loading and progress states, set expectations only when the timing or next action is known.

Internal concepts such as tokens, scopes, workflow states, or database objects belong in interface text only when they change the visitor's choice or action. Translate the consequence into ordinary language.

## Instructions

- State prerequisites before steps.
- Give one action per numbered step when sequence matters.
- Use the exact label, command, or destination the visitor will see.
- Explain the expected result after a consequential step.
- Put warnings immediately before the risky action.
- Include recovery or rollback guidance when failure is likely or costly.
- Move optional detail out of the main path without hiding necessary conditions.

## Errors and recovery

An error message should answer as many of these as the system can truthfully support:

1. What failed?
2. What was preserved or changed?
3. Why did it fail, if known and useful?
4. What can the visitor do now?

Do not guess a cause. If the system cannot distinguish causes, give a safe next action and a useful way to get help.

## Accessibility review

- Make control and link meaning understandable without nearby visual context.
- Do not rely on color, icons, or position alone.
- Keep labels and terminology stable between instructions and the interface.
- Use plain literal language for critical actions.
- Avoid idioms and culturally narrow metaphors where they could block comprehension.
- Check that screen-reader text adds missing meaning instead of duplicating visible text awkwardly.

Do not enforce character counts or reading-grade targets as universal laws. Use them as diagnostic signals, then judge the real audience, device, localization needs, and task risk.
