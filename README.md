# MemoryPalace: Long-Term Memory Architecture for Autonomous AI Agents

An experience-driven long-term memory system for AI agents that enables persistent learning, active knowledge capture, and intelligent forgetting detection.

## Architecture

```
┌─────────────────────────────────────────────┐
│           L0: Core Memory (≤2KB)            │
│  User preferences + identity + active SOPs   │
└─────────────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────┐
│        L1: Preference Memory (～50KB)        │
│  User patterns + platform rules + style      │
└─────────────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────┐
│       L2: Daily Logs (unbounded)            │
│  Raw events + conversations + decisions     │
└─────────────────────────────────────────────┘
                     ↓
┌─────────────────────────────────────────────┐
│           Knowledge Graph (neo4j-lite)      │
│  Entities + relations + confidence scores   │
└─────────────────────────────────────────────┘
```

## Key Features

- **Append-Only Memory**: Never delete facts, only mark as inactive
- **Hebbian Learning**: Connection strength increases with co-occurrence frequency
- **Proactive Alert System**: 4 alert types (staleness, corrections, orphans, queue)
- **Forgetting Detection**: Auto-detects entities not referenced in 30+ days
- **Cross-Agent Sync**: Share memory summaries with other agents via shared storage

## Installation

```bash
git clone https://github.com/guanqi0914/memory-palace.git
cd memory-palace
pip install -r requirements.txt
```

## Core Scripts

| Script | Purpose |
|--------|---------|
| `palace-engine.py` | Core memory engine with room-based event processing |
| `knowledge-active-capture.py` | Extract entities/events from daily logs |
| `forgetting-detection.py` | Find entities not referenced in 30+ days |
| `hebbian-monitor.py` | Monitor and update connection strengths |
| `meta-cognition.py` | Decision review and strategy improvement |
| `bm25_search.py` | Full-text search over memory using BM25 |

## Paper

This work is described in the paper: **MemoryPalace: Long-Term Memory Architecture for Autonomous AI Agents**

```
@misc{memorypalace2026,
  title={MemoryPalace: Long-Term Memory Architecture for Autonomous AI Agents},
  author={Anonymous},
  year={2026}
}
```

## License

MIT License
