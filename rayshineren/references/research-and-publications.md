# Research and Publication Reference

Use this file for RayshineRen research summaries, paper lists, research planning, related work, and formal profile drafting.

## Main research identity

RayshineRen's research centers on AI4PDE / AI4Science, with a transition:

```text
PINN-style continuous physics-informed learning
  -> EmPINN / DL-PINN / DeepONet variants
  -> PeRCNN discrete physics-encoded recurrent convolutional solvers
  -> time-step loss imbalance and long-term dependency
  -> AI4CFD / Navier-Stokes / reproducibility and weak baseline concerns
  -> AI for nuclear data evaluation with TRE / Transformer / EXFOR / ENDF / OpenMC
```

## Paper / manuscript inventory

Verify final metadata before formal external use.

| Work | RayshineRen role | Technical contribution / note | Status wording guidance |
|---|---|---|---|
| `基于多物理损失函数的偏微分方程智能求解方法` | first author | EmPINN and DL-PINN; combines dimension expansion, gradient-enhanced physics information, and variational physical loss for PDE solving | May describe as a published Chinese AI4PDE paper if the user confirms venue metadata. |
| `TaW-PeRCNN: Time-adaptive Weights Physics-encoded Recurrent Convolutional Neural Network for Solving PDEs` | first author | time-adaptive weights for multi-time-step loss imbalance in PeRCNN | Treat as ICONIP-related only if user confirms final proceedings details. |
| `MtS-PeRCNN: Multi-time Stepping Physics-encoded Recurrent Convolutional Neural Network for Solving PDEs` | first author | multi-time stepping weight update to improve convergence and extrapolation under large time steps | Treat as ICONIP-related only if user confirms final proceedings details. |
| `A-PeARCNN: a Physics-encoded AutoRegressive Convolutional Neural Network with AttentionNet for Solving PDEs` | co-first / equal contribution with Yibo Han, as previously indicated by user/context | sliding-window history, Coordinate Attention, AttentionNet, spatiotemporal autoregressive PeRCNN extension | Do not claim accepted unless user provides confirmation. |
| `TRE: Transfer-Regression-Ensemble model for Enhancing Nuclear Data Evaluation` | co-author | transfer learning from ENDF to EXFOR, ensemble regression, OpenMC validation for nuclear cross-section data | ACML 2024 / PMLR wording should be verified before formal citation. |
| `基于 Transformer 增强核数据评价` | co-author | Transformer-enhanced nuclear cross-section data evaluation | CORPHY 2024 wording should be verified before formal citation. |
| Undergraduate thesis `基于物理信息神经网络的偏微分方程求解方法研究` | author | EmPINN / VgEmPINN / GPI DeepONet lineage | Use as thesis/project background, not publication unless separately confirmed. |

## Research heuristics to reuse

1. **Baseline skepticism**: AI4CFD papers can be over-optimistic when comparing against weak numerical baselines. Require strong baselines and reproducible settings.
2. **Loss imbalance matters**: In PINN and PeRCNN lines, multi-loss or multi-time-step imbalance recurs. Ask whether the method is really solving architecture capacity, optimization weighting, or temporal error accumulation.
3. **Long-horizon validation**: For PDE dynamics, short-window training error is insufficient. Check extrapolation, stability, boundary handling, and long-term dependency.
4. **Engineering validation matters**: A paper idea should map to code, dataset, metrics, ablations, and failure cases; otherwise keep it as hypothesis.
5. **Hybrid method mindset**: Pure physics-informed or pure data-driven methods may be insufficient for complex PDEs; consider physics + data, operator learning, and sequence modeling.

## Recommended research output structure

For a new research task, produce:

- Problem statement and why prior work fails.
- Method lineage.
- Proposed contribution and novelty risk.
- Baselines: numerical, PINN-family, operator-learning, sequence/discrete solvers as applicable.
- Datasets/PDEs: Burgers, Poisson, reaction-diffusion, Navier-Stokes, nuclear cross sections, etc. only when relevant.
- Metrics: relative L2, MSE/RMSE/MAE/R2, long-time extrapolation, runtime, convergence, stability.
- Ablations: weight strategy, architecture component, time-step size, noise, boundary condition, data amount.
- Failure modes and how to falsify the idea.
- Venue/citation plan, marking unverified publication status clearly.
