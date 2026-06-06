# Project Guidance

Before adding new features, review the codebase like a senior VB.NET developer.

Your goals:
1. Keep the code readable for a human programmer.
2. Avoid giant files, giant methods, duplicated logic, and unclear names.
3. Prefer small classes/modules with clear responsibilities.
4. Do not over-engineer or create unnecessary abstractions.
5. Keep game logic separate from UI code where practical.
6. Add comments only where they explain why something exists, not obvious code.
7. Preserve existing behavior unless I explicitly ask to change it.
8. After changes, summarize what files changed and why.
9. Point out any code smells you noticed but did not fix.

If a method is getting hard to explain in one sentence, stop and suggest a refactor before continuing.

For this project, prioritize:
- Clear dinosaur/stat/ability data structures
- Combat logic that is easy to balance
- Evolution tree logic that is easy to expand
- No "everything happens in Form1.vb" disasters
- Simple save/load structure
- Names that make sense to a non-expert
