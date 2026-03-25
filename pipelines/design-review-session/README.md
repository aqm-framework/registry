# Design Review Session Pipeline

A **conversational session pipeline** where three specialists (architect, frontend dev, security engineer) discuss and reach consensus on a design proposal before implementation begins.

## Flow

```
[planner] → [design_review session] → [implementer]
                  ┌──┬──┬──┐
                  │  │  │  │  round-robin until all agree
                  ▼  ▼  ▼  ▼
            [architect] [frontend_dev] [security_engineer]
```

## Features Used

- **Session node** (`type: session`) with round-robin consensus
- **Mixed pipeline**: batch → session → batch
- **Real-time streaming** of conversation in CLI and web dashboard
- **Meeting transcript** (`transcript.md`) saved per task
- **Parameterization** for project type and tech stack

## Usage

```bash
aqm pull design-review-session
aqm run "Design a user authentication system with OAuth2 and MFA"
```

## Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `project_type` | `"web application"` | Type of project |
| `tech_stack` | `"TypeScript, React, Node.js"` | Primary technology stack |

## Tags

`session`, `design-review`, `architecture`, `security`, `multi-agent-discussion`
