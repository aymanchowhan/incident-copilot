# CLAUDE.md

## Project goal

incident-copilot is an AI DevOps incident-response agent. It watches a set of
instrumented microservices, detects incidents, investigates them using metrics,
logs, and traces, and proposes (eventually executes) remediations. It is built
in 10 phases.

**Current phase: 1** — three FastAPI demo services (`api-gateway`, `orders`,
`inventory`) plus Postgres running on a local kind cluster, with chaos scripts
that inject failures and record ground truth for later evaluation of the agent.

## Stack

- **Language / services:** Python, FastAPI
- **Agent:** LangGraph, MCP (tool servers)
- **Runtime:** Docker, Kubernetes (kind locally, EKS later)
- **Data:** Postgres
- **Observability:** OpenTelemetry, Prometheus, Grafana, Loki, Tempo

## Folder layout

```
app/          Demo services (phase 1: api-gateway/, orders/, inventory/)
chaos/        Failure-injection scripts
  records/    Ground-truth records of injected failures (gitignored for now)
k8s/          Kubernetes manifests (kind cluster, services, Postgres)
runbooks/     Incident runbooks the agent can consult
docs/         Project docs
  decision-log.md   Architecture / design decisions
  ai-usage-log.md   Log of AI-assisted work
```

Update this section when new top-level folders are added (e.g. for the agent,
MCP servers, or observability config in later phases).

## Working rules

1. **Explain before changing.** Before editing or creating files, say what you
   are about to change and why, then do it.
2. **Log AI usage.** After each meaningful task, add an entry to
   `docs/ai-usage-log.md` using the template in that file.
3. **Never commit secrets.** Do not commit `.env` files, credentials, tokens,
   kubeconfigs, or other secrets. Use `.env.example` for documenting required
   variables. Check `git status` / `git diff --cached` before committing.
