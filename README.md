Benchmarking the gap between AI agent hype and architectural reality. Mathematically rigorous evaluation framework that classifies agent implementations into three archetypes and measures the performance chasm between them.

<p align="center">
  <a href="https://github.com/Cre4T3Tiv3/ai-agents-reality-check" target="_blank">
    <img src="https://raw.githubusercontent.com/Cre4T3Tiv3/ai-agents-reality-check/main/docs/assets/ai_agents_reality_check_v0.1.0.jpeg" alt="AI Agents Reality Check v0.1.0" width="640"/>
  </a>
</p>

<p align="center">
  <a href="https://github.com/Cre4T3Tiv3/ai-agents-reality-check/releases/tag/v0.1.0">
    <img src="https://img.shields.io/badge/version-v0.1.0-brightgreen" alt="Version: v0.1.0">
  </a>
  <a href="https://github.com/Cre4T3Tiv3/ai-agents-reality-check/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/License-Apache_2.0-blue.svg" alt="License: Apache 2.0">
  </a>
  <a href="https://orcid.org/0009-0006-0322-7974">
    <img src="https://img.shields.io/badge/ORCID-0009--0006--0322--7974-A6CE39?logo=orcid&logoColor=white" alt="ORCID: 0009-0006-0322-7974">
  </a>
  <a href="https://bytestacklabs.com">
    <img src="https://img.shields.io/badge/Made%20by-ByteStack%20Labs-2ea44f" alt="ByteStack Labs">
  </a>
</p>

---

## The Thesis

Most systems marketed as "AI agents" are prompt-chained wrappers around LLM APIs. This benchmark quantifies the architectural difference with empirical evidence by simulating three agent archetypes under controlled conditions and measuring success rate, context retention, cost efficiency, and resilience under stress.

**The three archetypes:**

| Agent Type | Architecture | Planning | Memory | Recovery |
| --- | --- | --- | --- | --- |
| Wrapper Agent | Single LLM call | None | Stateless | No retry |
| Marketing Agent | Basic orchestration | Static | Ephemeral | Limited |
| Real Agent | Full autonomous system | Hierarchical | Semantic | Multi-strategy |

## Core Results

**Standard benchmark (5 iterations):**

| Agent Type | Success Rate | Context Retention | Cost per Success |
| --- | --- | --- | --- |
| Wrapper Agent | 20-27% | 11-13% | $0.008-$0.010 |
| Marketing Agent | 47-67% | 62-63% | $0.090-$0.129 |
| Real Agent | 93% | 93-94% | $0.031-$0.032 |

**Performance gap: 66-73 percentage points** between Real Agent and Wrapper Agent.

**Under stress (tool failures + network issues):** Real Agents maintain 75% success. Wrapper Agents collapse to 22%. Marketing Agents, which appeared functional in ideal conditions, drop to 25%, revealing that their orchestration layer provides no meaningful resilience.

**Network resilience testing:** Real Agents achieve a resilience factor of 5.17. Wrapper Agents score 0.59, meaning they perform almost 9x worse under unstable network conditions than the baseline would predict.

## The Multi-Agent Finding

Every ensemble pattern tested performed worse than individual Real Agents.

| Ensemble Pattern | Success Rate | vs Individual Real Agent |
| --- | --- | --- |
| Pipeline | 0.0% | -69.0% |
| Parallel | 22.2% | -46.7% |
| Hierarchical | 22.2% | -46.7% |
| Consensus | 22.2% | -46.7% |
| Specialization | 22.2% | -46.7% |

**0% positive synergy rate** across all patterns. Average ensemble advantage: -40%. Coordination overhead adds 0.5-1.5 seconds per task with no performance benefit.

## Quick Start

```bash
# Requires Python 3.11+ and UV package manager
git clone https://github.com/Cre4T3Tiv3/ai-agents-reality-check
cd ai-agents-reality-check
make install
```

### Run Benchmarks

```bash
make run                  # Standard 5-iteration benchmark
make run-enhanced         # Stress testing with tool failures
make run-ensemble         # Multi-agent collaboration benchmark
make run-network-test     # Network resilience testing
make run-comprehensive    # All enhanced features combined
```

### Analyze Results

```bash
make analyze-results      # Auto-detect and analyze latest results
make analyze-enhanced     # Enhanced results with 99% confidence intervals
make analyze-ensemble     # Ensemble collaboration analysis
make analyze-network      # Network resilience analysis
```

## Full Command Reference

**Installation:** `make install` (core), `make install-dev` (dev dependencies and hooks), `make version` (system info).

**Core benchmarking:** `make run`, `make run-random` (randomized task order), `make run-enhanced` (stress testing), `make run-debug` (verbose logging).

**Network conditions:** `make run-network-stable`, `make run-network-slow` (high latency), `make run-network-degraded` (packet loss), `make run-network-peak`, `make run-network-unstable`.

**Ensemble patterns:** `make ensemble-pipeline`, `make ensemble-consensus`, `make ensemble-hierarchical`, `make ensemble-quick`.

**Quality:** `make test-unit`, `make lint`, `make type-check`, `make check` (full QA suite).

All commands support custom arguments via `ARGS` parameter: `make run ARGS="--iterations 10 --quiet --seed 123"`.

## Documentation

- [Contributing](CONTRIBUTING.md) — Development setup and coding standards

## License

[Apache 2.0](LICENSE)
