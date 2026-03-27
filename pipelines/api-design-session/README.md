# API Design Session Pipeline

A **moderated session pipeline** where a backend architect leads a discussion with an API consumer and DevOps engineer to agree on API design. After consensus, a spec writer produces the formal API specification.

## Flow

```
[api_design_session] → [spec_writer]
   ┌──┬──┬──┐
   │  │  │  │  moderator-led rounds
   ▼  ▼  ▼  ▼
[backend_architect*] [api_consumer] [devops_engineer]
 (* = moderator & summary agent)
```

## Features Used

- **Moderated session** (`turn_order: moderator`, `method: moderator_decides`)
- **Multi-LLM**: Claude for discussion, Gemini for fast spec writing
- **Summary agent** produces structured output after consensus
- **Parameterization** for API style and auth method

## Usage

```bash
aqm pull api-design-session
aqm run "Design REST API for user management: CRUD, auth, roles"
```

## Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `api_style` | `"REST"` | API style (REST, GraphQL, gRPC) |
| `auth_method` | `"JWT"` | Authentication method |

## Tags

`session`, `api-design`, `moderated`, `multi-llm`, `openapi`
