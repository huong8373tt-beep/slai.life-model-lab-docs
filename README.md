# Slai Model Lab

Slai Model Lab is a private, multi-track model-training, model-runtime, and experimentation system that accompanies [Slai Agent Runtime](https://github.com/huong8373tt-beep/slai.life).

It covers experiments with text, speech, image, video, multimodal, and homegrown models. The work includes low-VRAM full-parameter training, quantized resident-training experiments, long-running checkpoint and resume workflows, model runtime work, and candidate-model evaluation.

This repository publishes experiment records, engineering milestones, and research direction. Core training code, private data, weights, prompts, machine configuration, and internal operating methods remain private.

## Current context

At today's personal-compute budget, Slai Agent Runtime relies primarily on cloud-model APIs for its main engineering work. Model Lab is a parallel, forward-looking effort: as personal compute, hardware efficiency, and model availability improve, individuals should be able to train, operate, and evaluate more of their own models.

The Runtime and the Lab have different roles:

```text
Slai Agent Runtime
→ carries goals through real tasks, tools, environments, tests, and verification

Slai Model Lab
→ studies private training, model operation, recovery, and candidate-model evaluation
```

Over time, the intended relationship is:

```text
real task experience from the Runtime
→ selection and review
→ private training material
→ training and candidate models
→ evaluation and regression checks
→ validated capability available to later Runtime work
```

The Runtime does not require self-trained models in order to work, and not every conversation, log, or tool result is automatically used for training.

## Recorded experiment lines

The Lab is not centered on one benchmark, one model family, or one modality. Recorded work includes:

- **Consumer-GPU experimentation:** local training and model-runtime work on an RTX 4070 SUPER with 12 GB VRAM.
- **Text-model training:** Qwen3.5-4B BF16 full-parameter long-run training beyond **20,000 steps**, with checkpoints and resume records.
- **Quantized resident-training experiments:** Qwen3.5-9B NF4 resident training (`seq512` / `batch4`) and Qwen3-14B NF4 resident training (`seq1024`) under constrained VRAM.
- **Larger-model continuation:** Qwen14B NF4 resident full-parameter continuation experiments with recorded long-run progress.
- **Image-model runtime work:** FLUX.2-klein 9B NF4 resident inference with BF16 chunked transient compute, including 512×512 and 1024×1024 probes.
- **Speech, vision, video, and multimodal work:** speech-training paths and data workflows; image, video, and multimodal experiment material and stress-test routes.
- **Homegrown-model work:** smaller self-built models, code and corpus training, and experiments with model structures and training strategies.
- **Long-run operation:** training profiles, queues, metrics, checkpoints, safe stopping, resume, and evaluation loops.

These are separate experiments with different models, configurations, dates, and goals. They are engineering records, not a single standardized benchmark or a claim that all approaches have the same quality characteristics.

## Design directions

### Training and inference as one longer lifecycle

A usual model lifecycle is simple:

```text
training → deployment → inference
```

Model Lab explores a longer lifecycle in which deployment and real work can produce experience that is later reviewed, trained, and evaluated:

```text
training → deployment → real tasks → reviewed experience
→ candidate training → evaluation → later deployment
```

The aim is not to assume that a model automatically becomes better from every interaction. The work focuses on screening, deduplication, evaluation, regression checks, and rollback before a candidate capability is used again.

### Live-model coordination

One research direction is coordination between training and inference for the same model lineage, with a longer-term goal of exploring how one live set of model weights can support both real-time inference and controlled training rather than forcing a permanent split between a training model and an inference model.

For example, an interactive request should be able to take priority while background training slows or pauses, then training can resume afterward with checkpoints and explicit state. This is an engineering and research direction, not a claim that arbitrary weight updates can safely run alongside real-time inference in every model or deployment.

### A practical path for personal models

The Lab does not claim that consumer hardware replaces large training clusters. It asks a different question: what can a person or small team train, run, recover, and evaluate with limited VRAM and a limited budget?

The current work builds the training, recovery, and evaluation foundation early. The longer-term goal is to be ready as personal hardware, cost efficiency, and accessible models make personal model operation and training more practical.

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
