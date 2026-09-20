# ID24 - Autonomous Navigation Penalty System

A computer-vision system that tracks a model car on a track using four
ceiling-like-mounted cameras and assigns penalties based on the car's position
relative to the track boundaries.

**Processing is offline.** Cameras record to disk and analysis is run afterwards.
Nothing needs to happen in real time, at least version 1.

## Start here

**[docs/PLAN.md](docs/PLAN.md)** - how the system works, the pipeline diagram,
the week-by-week plan, and what we still need to decide.

[docs/OPEN_QUESTIONS.md](docs/OPEN_QUESTIONS.md) - running list of unknowns.

## Development environment

- **Ubuntu 26.04 LTS** (via WSL2 on Windows)
- Python 3.x  ?

```bash
git clone https://github.com/Sairanyx/id24-racecar.git
cd id24-racecar
```

Keep the repository in the Linux filesystem (`~/dev/id24-racecar`), not under
`/mnt/c/`. Git is several times slower across the Windows bridge.

## Repository layout

```
configs/     YAML configuration - cameras, track geometry, penalty rules
data/        Recordings and derived data (NOT tracked by git)
docs/        Plan and open questions
notebooks/   Exploration only - never part of the pipeline
scripts/     Command-line entry points
src/id24/    Source code, one package per pipeline stage
tests/       Tests
```

## Working on this repository

`main` is protected. All I think should go through a branch and a pull request. Some ideas:

```bash
git checkout main
git pull
git checkout -b feat/my-thing
git add .
git commit -m "Describe what changed"
git push -u origin feat/my-thing
gh pr create
```

Branch naming: `feat/` for new work, `fix/` for bug fixes, `docs/` for
documentation.

### I guess a good idea would be:

1. **Not commit directly to `main`.**
2. **Not commit video, datasets or model weights.** They live in shared (not sure where, maybe R&D Insight lab pc?)
   storage, not in git. It has been gitignored but try to make sure.

## Status

Week 1 - meeting with Amin, getting to know each other, research on project.

Week 2 - environment setup, discussion on architecture, camera installation.

Open questions are tracked in [docs/OPEN_QUESTIONS.md](docs/OPEN_QUESTIONS.md).
