---
layout: post
order: 1
title: Mechanical assembly design and selection
description: Deterministic generation, screening and mechanical verification of shaft-pulley-bearing assemblies.
skills: [Mechanical design, CAD automation, Tolerancing, Structural sizing / FEM, Rotating dynamics, Design space exploration]
permalink: /projects/mechanical-assembly-design/
---

## Context
The study concerns a belt-drive assembly built from a **shaft, pulley, two bearings, housings and a base**. The objective is to compare admissible mechanical architectures while keeping the design process deterministic and traceable.

## Shape grammar
Each candidate keeps the sequence of rules that generated it.

```julia
ShapeGrammarDerivation(rules = [
    Symbol("support_", candidate.support_family),
    Symbol("base_", candidate.base_family),
    Symbol("locate_", candidate.locating_bearing),
    Symbol("stack_", candidate.stack_layout),
    Symbol("torque_", candidate.torque_interface),
    Symbol("retain_", candidate.axial_retention),
])
```

The grammar can write **314,928 combinations**. A randomised traversal was stopped after **14,624 sampled combinations**. This value is the sample size, not a filtering stage.

## Progressive screening
<div class="pipeline"><div><b>1. Analytical feasibility</b><small>14,624 → 2,266<br>Tolerance chain, kinematics, budget, strength, bearing life, bolting, thermal growth and fatigue.</small></div><div><b>2. Campbell screening</b><small>2,266 → 2,000<br>Analytical rotating-order screening from 0 to 3,000 rpm.</small></div><div><b>3. CAD and FEM</b><small>2,000 → 1,935 solved → 1,654 accepted.</small></div><div><b>4. Selection</b><small>1,654 → 51 exact Pareto solutions → 9 final architectures.</small></div></div>

## Exploration and selection of concepts
The grammar generates a large number of architectures. Candidates are compared on **mass, cost, unbalance amplitude and resonance margin**. Retained concepts are then inspected individually with their geometry and validation results.

<div class="metric-strip"><div><b>314,928</b><span>possible combinations</span></div><div><b>14,624</b><span>sampled</span></div><div><b>1,654</b><span>accepted after FEM</span></div><div><b>9</b><span>final architectures</span></div></div>

## Tolerance chain
| Method | Reserved tolerance | Remaining margin |
|---|---:|---:|
| Worst case | 0.840 mm | **41.410 mm** |
| RSS | 0.359 mm | 41.891 mm |
| Bender | 0.538 mm | 41.712 mm |
| Six Sigma | 0.779 mm | 41.471 mm |

The tolerance chain does not govern the sizing of this architecture.

## Mechanical verification
For reference candidate ASM_C229583, the calculated speed ceiling is **4,936 rpm** for a 3,000 rpm requirement. The model also gives **362,904 h bearing life**, a **fatigue factor of 10.58** and **0.0313 mm shaft deflection**.

## Result
The reference design weighs 0.775 kg and costs €423. Candidate ASM_C288079 reaches **0.469 kg and €416**, corresponding to **39.5% lower mass and 1.6% lower cost** than the reference.
