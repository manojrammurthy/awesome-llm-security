# LiteLLM Attack

## Summary

The LiteLLM case represents a class of risks where a model gateway or proxy becomes a high-value target because it centralizes credentials, routing logic, usage controls, and administrative functions.

## What Happened

- Organizations deployed LiteLLM as a unified proxy across multiple model providers.
- In insecure setups, administrative surfaces or weak authentication created opportunities for unauthorized access or abuse.
- Because the proxy sat in front of several providers, one compromise could affect multiple downstream integrations.

## Why It Mattered

- The gateway was a concentration point for secrets and policy.
- Misconfiguration could expose model access, spend controls, logs, or tenant boundaries.
- A thin infrastructure layer ended up carrying disproportionate security impact.

## Root Causes

- Public exposure of internal admin or management endpoints
- Weak or missing authentication
- Shared credentials across providers or tenants
- Overconfidence that a routing proxy was low risk infrastructure

## Defensive Takeaways

- Put model gateways behind strong authentication and private network boundaries.
- Use separate provider keys per environment and tenant where possible.
- Log administrative changes and alert on unusual proxy activity.
- Review open source defaults before production deployment.
