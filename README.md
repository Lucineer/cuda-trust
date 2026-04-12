# cuda-trust

Trust engine — grows slowly, decays fast, multi-context trust profiles with Bayesian fusion (Rust)

Part of the Cocapn fleet layer — how vessels coordinate, route, and scale.

## What It Does

### Key Types

- `TrustScore` — core data structure
- `TrustProfile` — core data structure
- `TrustRegistry` — core data structure
- `TrustSummary` — core data structure

## Quick Start

```bash
# Clone
git clone https://github.com/Lucineer/cuda-trust.git
cd cuda-trust

# Build
cargo build

# Run tests
cargo test
```

## Usage

```rust
use cuda_trust::*;

// See src/lib.rs for full API
// 12 unit tests included
```

### Available Implementations

- `TrustScore` — see source for methods
- `TrustProfile` — see source for methods
- `TrustRegistry` — see source for methods

## Testing

```bash
cargo test
```

12 unit tests covering core functionality.

## Architecture

This crate is part of the **Cocapn Fleet** — a git-native multi-agent ecosystem.

- **Category**: fleet
- **Language**: Rust
- **Dependencies**: See `Cargo.toml`
- **Status**: Active development

## Related Crates

- [cuda-semantic-router](https://github.com/Lucineer/cuda-semantic-router)
- [cuda-fleet-topology](https://github.com/Lucineer/cuda-fleet-topology)
- [cuda-adaptive-rate](https://github.com/Lucineer/cuda-adaptive-rate)
- [cuda-bottleneck](https://github.com/Lucineer/cuda-bottleneck)
- [cuda-fleet-health](https://github.com/Lucineer/cuda-fleet-health)
- [cuda-swarm-agent](https://github.com/Lucineer/cuda-swarm-agent)

## Fleet Position

```
Casey (Captain)
├── JetsonClaw1 (Lucineer realm — hardware, low-level systems, fleet infrastructure)
├── Oracle1 (SuperInstance — lighthouse, architecture, consensus)
└── Babel (SuperInstance — multilingual scout)
```

## Contributing

This is a fleet vessel component. Fork it, improve it, push a bottle to `message-in-a-bottle/for-jetsonclaw1/`.



## Iron-to-Iron (I2I) Integration

The trust engine communicates fleet trust states via the I2I protocol. Trust scores propagate between vessels using `TRUST_UPDATE` messages:

```json
{
  "type": "TRUST_UPDATE",
  "from_vessel": "jetsonclaw1",
  "to_vessel": "oracle1",
  "trust_scores": {
    "confidence": 0.87,
    "energy": 0.72,
    "competence": 0.91,
    "consistency": 0.85
  },
  "evidence": [
    {"source": "commit_quality", "value": 0.9, "notes": "37/39 tests passing"},
    {"source": "response_time", "value": 0.7, "notes": "median 4.2h between I2I messages"}
  ],
  "timestamp": "2026-04-11T23:00:00Z"
}
```

### Trust Propagation Rules

1. **Bayesian fusion**: New evidence updates prior beliefs using Bayes' theorem
2. **Decay**: Trust scores decay 5% per day without new evidence
3. **Threshold**: Trust below 0.3 triggers `TRUST_ALERT`; below 0.1 triggers `TRUST_REVOKE`
4. **Reciprocity**: If vessel A trusts B at 0.9, B's trust in A gets a 0.1 bonus (goodwill signal)

### Integration with cuda-energy

Trust scores feed into the energy budget: high-trust vessels get priority resource allocation. Low-trust vessels have reduced token budgets (energy conservation under uncertainty).

## License

MIT

---

*Built by JetsonClaw1 — part of the Cocapn fleet*
*See [cocapn-fleet-readme](https://github.com/Lucineer/cocapn-fleet-readme) for the full fleet roadmap*
