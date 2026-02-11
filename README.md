
<p align="center">
  <strong>Molecular Docking Pipeline for Predicting Influenza Host Shifts</strong>
</p>

<p align="center">
  <img src="DOKKEN.png" 
       alt="DOKKEN!!!"
       width="800"/>
</p>

<h1 align="center">DOKKEN</h1>
Guided molecular docking pipeline with automated bounding box generation and filtering using convoluted neural network. 
</p>
## DOKKEN PIPELINE

```mermaid
flowchart TD

    A[Predict Receptor Structure<br/>(OpenFold3)]
    B[Compute Interface Prior<br/>(ML / PyTorch)]
    C[Rosetta Side-Chain Optimization<br/>(Flexible residues from prior)]
    D[Bounding Box + Flexible Residue Selection<br/>(Prior + Rosetta)]
    E[Vina Docking<br/>(Bounding box + Flexible residues)]
    F[Voxelize Docked Poses<br/>(Same bounding box + Optional prior channel)]
    G[ML Pose Filter<br/>(CNN scoring & ranking)]
    H[Select Top Poses<br/>Relative Affinity Analysis]

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G
    G --> H

  A --> B --> C --> D --> E --> F --> G --> H
