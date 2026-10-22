# Slai Model Lab

Slai Model Lab is a private, multi-track model-training, model-runtime, and experimentation system that accompanies [Slai Agent Runtime](https://github.com/huong8373tt-beep/slai.life).

It covers text, speech, image, video, multimodal, and homegrown-model work. The Lab includes low-VRAM full-parameter training, NF4 resident-training experiments, long-running checkpoint and resume workflows, model-runtime work, and candidate-model evaluation.

This repository publishes experiment records, engineering milestones, and research direction. Core training code, private data, weights, prompts, machine configuration, and internal operating methods remain private.

## Current context

At today's personal-compute budget, Slai Agent Runtime relies primarily on capable cloud-model APIs for its main engineering work. Model Lab is the paired, forward-looking effort: as personal compute, hardware efficiency, and accessible models improve, individuals should be able to train, operate, and evaluate more of their own models.

The longer-term aim is a complete personal loop: when personally deployed models can approach the capability now accessed through cloud APIs, Slai can use real work to improve and evaluate its own model capability, then return validated capability to later work.

```text
Slai Agent Runtime
→ carries goals through real tasks, tools, environments, tests, and verification

Slai Model Lab
→ trains, runs, recovers, and evaluates candidate models for later Runtime work
```

## From real work to model improvement

Slai Agent Runtime works in real software, device, and service environments. That work produces reviewable experience: task results, feedback, reusable material, successful paths, failures, and evidence.

Model Lab explores how Slai Agent Runtime itself can use controlled selection and evaluation methods to identify suitable private training material from that experience, operate training workflows, and assist with evaluating, training, and verifying candidate models.

```text
real-world Runtime work
→ reviewable experience and selected material
→ private training and candidate models
→ evaluation and regression checks
→ validated capability for later Runtime work, or rollback
```

This is a controlled improvement loop, not automatic training on every conversation, log, or tool result. Training material and candidate capabilities are selected and validated before use.

## Live Slai in the training environment

Model Lab includes a local Slai Agent Runtime inside its training environment. It is not a separate demonstration loaded only after training finishes: while a training run is active, Slai can remain alive for direct conversation and inference.

Training and live interaction belong to the same model system rather than permanently separate “training model” and “serving model” phases. The runtime, training process, checkpoints, and recovery paths coordinate a longer lifecycle in which Slai can be used, trained, saved, resumed, evaluated, and either continued or rolled back.

```text
live Slai conversation and inference
+ ongoing model training
+ task, memory, and tool work
+ checkpoints, recovery, and candidate evaluation
```

This is the reason for combining an Agent Runtime with a training system: real work can provide experience, Slai can help organize and evaluate it, and training can improve candidate capability without losing version or recovery boundaries. The work continues to improve how interactive work and training share resources safely; it does not treat every live interaction as an immediate, unreviewed weight update.

## Recorded experiment lines

The Lab is not centered on one benchmark, one model family, or one modality. Recorded work includes:

- **Consumer-GPU experimentation:** local training and model-runtime work on an RTX 4070 SUPER with 12 GB VRAM.
- **Full-parameter rather than adapter-only training:** the listed full-parameter routes keep the main model parameters in the training path. They are not LoRA or QLoRA adapter-only tuning that freezes the main model and trains only a small adapter.
- **BF16 full-parameter long runs:** Qwen3.5-4B BF16 full-parameter training beyond **20,000 steps**, with checkpoints and resume records.
- **NF4 resident full-parameter experiments:** Qwen3.5-9B NF4 resident training (`seq512` / `batch4`), Qwen3-14B NF4 resident training (`seq1024`), and Qwen14B NF4 resident full-parameter continuation routes under constrained VRAM.
- **Image-model runtime work:** FLUX.2-klein 9B NF4 resident inference with BF16 chunked transient compute, including 512×512 and 1024×1024 probes.
- **Speech, vision, video, and multimodal work:** speech-training paths and data workflows; image, video, and multimodal experiment material and stress-test routes.
- **Homegrown-model work:** smaller self-built models, code and corpus training, and experiments with model structures and training strategies.
- **Long-run operation:** training profiles, queues, metrics, checkpoints, safe stopping, resume, and evaluation loops.

These are separate experiments with different models, configurations, dates, and goals. They are engineering records, not a single standardized benchmark or a claim that all approaches have the same quality characteristics.

## Design directions

### A longer model lifecycle

A usual model lifecycle is simple:

```text
training → deployment → inference
```

Model Lab works toward a longer, controlled lifecycle:

```text
training → live use → real tasks → reviewed experience
→ candidate training → evaluation → later use or rollback
```

The goal is not to assume that a model automatically improves from every interaction. It is to make real-world experience useful only after screening, deduplication, evaluation, regression checks, and versioned rollback.

### A practical path for personal models

The Lab does not claim that consumer hardware replaces large training clusters. It asks a different question: what can a person or small team train, run, recover, and evaluate with limited VRAM and a limited budget?

The current work builds that foundation early. As personal hardware, cost efficiency, and accessible models improve, the aim is for personally deployed models to take on more of the capability that currently requires cloud APIs—and for the Runtime, experience, training, evaluation, and later use to form one practical loop.

## Scope and boundaries

This repository shares:

```text
experiment directions
recorded training and runtime milestones
hardware and engineering scope
research goals
```

It does not share:

```text
core source code
private datasets and curated experience material
model weights
keys, accounts, or device configuration
full logs and internal operating methods
```

For public records of Slai's cross-platform Runtime, upstream contributions, and benchmark runs, see [Slai Agent Runtime](https://github.com/huong8373tt-beep/slai.life).

## Collaboration

We welcome conversations around AI and agent research, continual learning, model training and optimization, model-runtime systems, compute-efficient experimentation, and research infrastructure.