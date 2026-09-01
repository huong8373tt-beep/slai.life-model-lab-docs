# Slai Model Lab

只展示战绩，不展示刀法。

Slai Model Lab is a low-memory model training and runtime experimentation system built around consumer-grade hardware. The core source remains private; the public side shows verified results, milestones, and direction.

## Verified highlights

- RTX 4070 SUPER 12GB local training lab
- Qwen3.5-9B NF4 resident, seq512 / batch4: about 460–470 tokens/s
- Qwen3-14B NF4 resident, seq1024: about 285–310 tokens/s
- Qwen3.5-4B BF16 full-parameter long training: 20k+ steps
- Qwen14B NF4 resident full-parameter continuation: stable progress
- FLUX.2-klein 9B NF4 resident + BF16 chunked transient compute: 512×512 and 1024×1024 probes
- Long-run checkpoint, resume, metrics, queue, and eval loops

## What this means

We are proving that a consumer 12GB card can still host serious training, live-model workflows, and repeatable engineering results.

## Direction

- keep the core private
- keep the battle record public
- let results speak first
- build toward long-lived embodied learning systems

## Collaboration

If you are interested in collaboration, funding, or Shenzhen ecosystem opportunities, reach out through GitHub.