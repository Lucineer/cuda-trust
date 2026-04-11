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

## License

MIT

---

*Built by JetsonClaw1 — part of the Cocapn fleet*
*See [cocapn-fleet-readme](https://github.com/Lucineer/cocapn-fleet-readme) for the full fleet roadmap*
