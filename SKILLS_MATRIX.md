# Skills matrix — hypothesis, not certification

Ratings here are **provisional qualitative impressions from the supplied strategy**, not assessments of competence.

| Area | Baseline impression | Next proof |
|---|---|---|
| Agent implementation / orchestration | Strong foundation | Reliable orchestration with traces, tests, safe permission boundaries |
| LLM systems | Good exposure | Benchmark serving, KV cache, batching, routing and inference economics |
| Distributed systems | Relevant experience; critical priority | Architecture + failure-injection + idempotency/recovery proof |
| Technical leadership | Developing; critical priority | ADR-led review, mentoring and documented cross-team trade-offs |
| AI security/governance | Requires assessed proof | Threat model, tool authorization and audit trail |
| Business / economics | Requires assessed proof | Cost per successful operation and build-vs-buy case |
| Coding/DSA | Ongoing practice | Timed coding, concurrency and service implementation evidence |
| Post-training/RL | Selective learning | Explain DPO/GRPO and run one targeted experiment if valuable |

## Rating rubric (use during quarterly review)

- **0:** not encountered.
- **1:** can explain fundamentals and limitations.
- **2:** built a small working example and tested it.
- **3:** operated in a relevant environment; can diagnose trade-offs and failure.
- **4:** architected/reviewed across team boundaries with measured outcome.

**Initial scores: unassigned** until tested. Attach commit links, PRs, benchmarks, sanitized evidence or written explanations before scoring.

## Questions for a baseline architecture assessment

1. Explain what happens when an agent retries a non-idempotent tool call.
2. How would you estimate p95 latency when three tool calls run in parallel?
3. When would a durable queue beat direct HTTP orchestration?
4. What changes in a model-serving system under concurrent requests and large KV caches?
5. How will you detect a confidently wrong root-cause analysis?
6. How do you enforce tool permissions and guarantee human approval before remediation?
7. Which metrics let you compare model A vs model B on accuracy, risk and cost?
8. How would you present the architecture's build-vs-buy decision to a director?
