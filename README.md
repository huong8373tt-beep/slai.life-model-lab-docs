# Slai Model Lab

Slai Model Lab is a multi-track model-training, live-model-runtime, and experimentation system that accompanies [Slai Agent Runtime](https://github.com/huong8373tt-beep/slai.agent.runtime).

It covers text, speech, image, video, multimodal, and homegrown-model work. The Lab includes low-VRAM full-parameter training, NF4 resident-training experiments, live QLoRA adaptation for fast short-term memory, long-running checkpoint and resume workflows, live model-runtime work, and candidate-model evaluation.

This repository records experiments, engineering milestones, and research directions.

## Current context

Slai Agent Runtime currently uses capable cloud-model APIs for most engineering work. Model Lab develops the longer-term path for training, operating, and evaluating personally deployed models as personal compute, hardware efficiency, and model accessibility continue to improve.

The longer-term aim is a complete personal loop: real work informs model improvement and evaluation, and validated capabilities return to later Runtime work.

```text
Slai Agent Runtime
→ carries goals through real tasks, tools, environments, tests, and verification

Slai Model Lab
→ trains, runs, recovers, and evaluates candidate models for later Runtime work
```

## From real work to model improvement

Slai Agent Runtime works in software, device, and service environments. That work produces task results, feedback, reusable material, successful paths, failures, and evidence.

Model Lab studies how selected experience can support training workflows and candidate-model evaluation.

```text
real-world Runtime work
→ reviewable experience and selected material
→ short-term adaptation or candidate training
→ evaluation and regression checks
→ validated capability for later Runtime work, or rollback
```

Training material and candidate capabilities are selected and evaluated before use.

## Live Slai in the training environment

`lab_slai_body` keeps a local Slai Agent Runtime inside the training environment. During a training run, Slai remains available for direct conversation, inference, and Runtime task execution.

Training and live interaction belong to the same model system. The Runtime, training process, checkpoints, and recovery paths support a longer lifecycle in which Slai can be used, trained, saved, resumed, evaluated, and continued or rolled back.

```text
live Slai conversation, inference, and task execution
+ ongoing model training
+ task, memory, and tool capabilities
+ checkpoints, recovery, and candidate evaluation
```

Real work can provide experience, Slai can help organize and evaluate it, and training can improve candidate capability within versioned recovery boundaries.

## Two learning paths

The Lab keeps fast adaptation separate from longer-term weight consolidation.

```text
selected near-term feedback or behavior correction
→ QLoRA adaptation
→ evaluate
→ keep or roll back

selected experience
→ full-parameter candidate training
→ evaluate and regression-check
→ promote for later use or roll back
```

**Live QLoRA** provides a fast, short-term memory and adaptation path. Selected feedback can be applied through a small adapter and evaluated while the live Slai system continues to run.

**NF4 resident** routes use train-time weight compression under constrained VRAM while retaining the main model parameters in the training path. They support longer-term weight internalization and use separate quality, regression, and stability checks before later use.

## Recorded experiment lines

- **Consumer-GPU experimentation:** local training and live model-runtime work on an RTX 4070 SUPER with 12 GB VRAM.
- **BF16 full-parameter long runs:** Qwen3.5-4B BF16 full-parameter training beyond **20,000 steps**, with checkpoints and resume records.
- **NF4 resident full-parameter experiments:** Qwen3.5-9B NF4 resident training (`seq512` / `batch4`), Qwen3-14B NF4 resident training (`seq1024`), and Qwen14B NF4 resident full-parameter continuation routes under constrained VRAM.
- **Image-model runtime work:** FLUX.2-klein 9B NF4 resident inference with BF16 chunked transient compute, including 512×512 and 1024×1024 probes.
- **Speech, vision, video, and multimodal work:** speech-training paths and data workflows; image, video, and multimodal experiment material and stress-test routes.
- **Homegrown-model work:** smaller self-built models, code and corpus training, and experiments with model structures and training strategies.
- **Long-run operation:** training profiles, queues, metrics, checkpoints, safe stopping, resume, and evaluation loops.

## Design directions

### A longer model lifecycle

```text
training → deployment → inference
```

Model Lab develops a longer lifecycle:

```text
training → live use → real tasks → reviewed experience
→ short-term adaptation or candidate training
→ evaluation → later use or rollback
```

Real-world experience enters later work through screening, deduplication, evaluation, regression checks, and versioned rollback.

### A practical path for personal models

The Lab investigates what individuals and small teams can train, run, recover, and evaluate with limited VRAM and compute budgets.

As personal hardware, cost efficiency, and accessible models improve, personally deployed models can take on more capability alongside cloud APIs. The Runtime, experience, training, evaluation, and later use form one practical loop.

## Collaboration

We welcome conversations around AI and agent research, continual learning, model training and optimization, model-runtime systems, compute-efficient experimentation, and research infrastructure.