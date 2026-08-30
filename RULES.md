# Team Development Rules

## Git

1. Never directly push to main.
2. Every feature uses a feature branch.
3. Every feature requires a Pull Request.
4. At least one team member reviews the PR.
5. main must remain working.

## Branch Naming

feature/frontend-*
feature/backend-*
feature/ai-*
feature/database-*
feature/logistics-*
feature/testing-*

Example:

feature/frontend-login

## Commits

Good:

Add farmer registration API

Bad:

changes
final
final2
working
asdf

## AI Coding Rules

Before coding, AI must understand:

- PRD.md
- ARCHITECTURE.md
- RULES.md
- DESIGN.md
- AI_CONTEXT.md

AI must:

- Modify only required files
- Avoid unrelated changes
- Explain changes
- Run tests
- Follow existing architecture
- Avoid unnecessary dependencies

## Forbidden

Do not:

- Commit passwords
- Commit API keys
- Commit .env
- Delete another member's code
- Rewrite unrelated modules
- Change database schema without discussion
- Change API contracts without informing affected members
- Install unnecessary packages

## Review

Before merging:

- Code runs
- No obvious errors
- Feature tested
- Documentation updated if required