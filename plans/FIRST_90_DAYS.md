# First 90 days: foundational architecture → production reliability → influence

**Start:** 2026-10-27. **End:** 2027-01-24. **Target capacity:** 8–10 focused hours/week (adjust around job demands).

## Days 1–30: architecture foundations (Oct 27–Nov 25)

- [ ] **1. Architecture review:** map a permitted or synthetic incident-intelligence system, dependencies, data flow, synchronous and async boundaries, security, throughput and scaling assumptions.
- [ ] **2. Decisions and failure paths:** write at least one ADR, a failure-mode table with detection/containment/recovery, and a deployment/recovery diagram.
- [ ] **3. Baseline metrics:** instrument task success rate, p50/p95 end-to-end latency, LLM token/call counts and estimated cost per successful task. Document workload and sample size.

**Week 1:** scope the system, draw the request/incident path, list unknowns and open questions. Review *why* queues, retries and idempotency matter before selecting implementations.

## Days 31–60: production hardening (Nov 26–Dec 25)

- [ ] **4. Observability and evaluation:** end-to-end trace ID, step/span events, quality rubric, curated synthetic/authorized incidents and failure taxonomy.
- [ ] **5. Context benchmark:** hold a fixed evaluation set constant; compare baseline context vs summarized/compacted context, measuring success, token use, latency and regressions.
- [ ] **6. Recovery tests:** inject timeout, dropped messages, pod restart or tool error; demonstrate bounded retries, deduplication and explicit safe failure states.

## Days 61–90: leadership evidence (Dec 26–Jan 24)

- [ ] **7. Architecture proposal:** requirements, system components, interfaces, reliability/security, alternatives, cost envelope and rollout plan.
- [ ] **8. Technical review:** present trade-offs, benchmarks, risks and unresolved decisions to a peer group or simulated review; record questions and revisions.
- [ ] **9. Case study:** publish a sanitized/public write-up or authorized internal note with problem, architecture, measured outcomes and lessons.

## Quality gate for each item

1. Commit a reproducible artifact (design, code, test, dataset spec or benchmark).
2. Describe why the choice works and when it breaks.
3. Add a link to the corresponding GitHub issue.
4. Only then mark it **Done** in [TRACKER](../TRACKER.md).

**Safety:** agent diagnosis is read-only by default. Do not connect experiments to unauthorized production tools. Remediation requires explicit human approval and bounded permissions.
