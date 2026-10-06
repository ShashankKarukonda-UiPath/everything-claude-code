# Development Workflow

> This file extends [common/git-workflow.md](./git-workflow.md) with the full feature development process that happens before git operations.

The Feature Implementation Workflow describes the development pipeline: research, planning, TDD, code review, and then committing to git.

## Feature Implementation Workflow

0. **Research & Reuse** _(before any new implementation)_
   - **Reuse internal code first:** Search the current repository, sibling repositories, and existing shared/internal libraries for implementations, helpers, and conventions before writing anything new.
   - **Primary docs second:** Confirm API behavior and version-specific details from the dependency's official documentation or the source already vendored in the project.
   - **External search only with permission:** Do not run public web, GitHub, or third-party documentation/search services (e.g. `gh search`, Context7, Exa) unless the user asks for it. When you do, never include proprietary code, internal names, hostnames, customer data, or secrets in queries.
   - **New dependencies need approval:** Prefer libraries already used in the project. Propose any new package to the user with its license and maintenance status; do not add it without approval.
   - **No copying external code without approval:** Do not fork, port, or paste open-source code into the codebase unless the user approves it after a license check.

1. **Plan First**
   - Use **planner** agent to create implementation plan
   - Generate planning docs before coding: PRD, architecture, system_design, tech_doc, task_list
   - Identify dependencies and risks
   - Break down into phases

2. **TDD Approach**
   - Use **tdd-guide** agent
   - Write tests first (RED)
   - Implement to pass tests (GREEN)
   - Refactor (IMPROVE)
   - Verify 80%+ coverage

3. **Code Review**
   - Use **code-reviewer** agent immediately after writing code
   - Address CRITICAL and HIGH issues
   - Fix MEDIUM issues when possible

4. **Commit & Push** _(only when the user asks)_
   - Never commit, push, or open a PR unless the user explicitly requests it
   - Detailed commit messages
   - Follow conventional commits format
   - See [git-workflow.md](./git-workflow.md) for commit message format and PR process

5. **Pre-Review Checks**
   - Verify all automated checks (CI/CD) are passing
   - Resolve any merge conflicts
   - Ensure branch is up to date with target branch
   - Only request review after these checks pass
