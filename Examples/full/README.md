# Full Example - Production Agent

This is a complete production-ready Resonix - Skill setup with all features.

## Files Needed

```
full/
├── CONFIG/agent.yaml
├── HEARTBEAT.md
├── MEMORY.md
├── MEMORY_INDEX.md
├── memory/              # Daily logs
│   └── 2026-01-01.md
├── semantic/            # Knowledge base
│   └── topic-name.md
└── Skills/              # Custom skills
    └── my-skill/
        └── SKILL.md
```

## Configuration

```yaml
agent:
  name: "Production Agent"
  description: "Full-featured AI agent"
  timezone: "Asia/Shanghai"
  language: "en"

memory:
  enabled: true
  storage:
    episodic: "./memory"
    semantic: "./semantic"
    working: "./HEARTBEAT.md"
    meta: "./MEMORY.md"
    index: "./MEMORY_INDEX.md"
  retrieval:
    importance_threshold: 5
    time_decay: 0.9
    max_results: 10
  cleanup:
    auto_consolidate: true
    consolidate_interval: 86400

learning:
  enabled: true
  modes:
    passive: true
    active: true
    scheduled: true
  sources:
    web_search: true
    browsing: true
    apis: true
  limits:
    max_daily: 20
    min_importance: 5

skills:
  enabled: true
  paths:
    - "./Skills"
    - "~/.openclaw/skills"
  auto_discover: true
  lazy_load: true

workflows:
  heartbeat:
    enabled: true
    interval: 1800
  cron:
    enabled: true

safety:
  confirm_external: true
  confirm_delete: true
```

## Directory Setup

```bash
# Create all directories
mkdir -p memory semantic Skills/my-skill

# Initialize memory files
touch HEARTBEAT.md MEMORY_INDEX.md
echo "# My Agent Memory" > MEMORY.md
```

## Features Included

✅ Multi-layer memory (episodic, semantic, procedural, working)
✅ Autonomous learning (web search, browsing, APIs)
✅ Skill system (auto-discovery, lazy loading)
✅ Heartbeat workflows (periodic checks)
✅ Cron scheduling
✅ Safety controls

## Use Cases

- Production deployments
- Learning agent setup
- Complex automation workflows
- Research and development

## Customization

See individual docs:
- [Core/memory.md](../Core/memory.md)
- [Core/learning.md](../Core/learning.md)
- [Core/skills.md](../Core/skills.md)
