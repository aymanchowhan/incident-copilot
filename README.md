# incident-copilot

An AI DevOps incident-response agent. It monitors instrumented microservices on
Kubernetes, investigates incidents using metrics, logs, and traces
(Prometheus, Loki, Tempo via OpenTelemetry), and proposes remediations. Built
with Python, FastAPI, LangGraph, and MCP.

The project is developed in 10 phases. Phase 1 sets up three demo FastAPI
services (`api-gateway`, `orders`, `inventory`) and Postgres on a local kind
cluster, plus chaos scripts that inject failures and record ground truth.
