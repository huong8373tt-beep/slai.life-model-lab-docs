# Slai Model Lab

Show the battle record. Keep the playbook private.

Slai Model Lab is a low-VRAM model training and agent experimentation system focused on model training, continual learning, and runtime coordination.

It explores how far persistent training, continual learning, and intelligent-agent workflows can be pushed under constrained compute and memory.

The core source code, training assets, and internal methods remain private. The public side focuses on verifiable results, technical milestones, and development direction.

## Verified Highlights

- RTX 4070 SUPER 12GB local model training and runtime experimentation
- Qwen3.5-9B NF4 resident training, seq512 / batch4 at approximately 460–470 tokens/s
- Qwen3-14B NF4 resident training, seq1024 at approximately 285–310 tokens/s
- Qwen3.5-4B BF16 full-parameter long-run training exceeding 20,000 steps
- Qwen14B NF4 resident full-parameter continuation with stable long-run progress
- FLUX.2-klein 9B NF4 resident inference with BF16 chunked transient compute, including 512×512 and 1024×1024 probes
- Long-running checkpoint, resume, metrics, queue, and evaluation loops
- Repeatable experiments across model training, runtime execution, and agent workflows

## What We Are Exploring

Large-scale compute is powerful, but it is not the only environment in which meaningful experimentation can happen.

Slai Model Lab explores practical approaches for making limited VRAM and consumer hardware support long-running training, continual learning experiments, live-model workflows, and persistent agent systems.

The goal is not to claim that consumer hardware can replace large-scale infrastructure.

The goal is to discover how far it can be pushed.

## Direction

- Keep the core private.
- Keep the battle record public.
- Let verified results speak first.
- Build toward long-lived embodied learning systems.

Slai Model Lab is not built around a single benchmark or a single model.

It is an ongoing exploration of how constrained compute can be turned into persistent learning capability.

## Collaboration

We are open to collaboration and conversations around:

- AI and agent research
- Continual learning
- Model training and optimization
- Runtime systems
- Compute-efficient experimentation
- Research infrastructure
- Funding and strategic partnerships

If you are interested in working together, feel free to reach out through GitHub.
