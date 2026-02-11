
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

## DOKKEN PIPELINE

```mermaid
flowchart LR

A["Predict Receptor Structure - OpenFold3"]
B["Compute Interface Prior - ML PyTorch"]
C["Rosetta Side Chain Optimization"]
D["Bounding Box and Flexible Residues"]
E["Vina Docking"]
F["Voxelize Docked Poses"]
G["CNN Pose Filter and Ranking"]
H["Select Top Poses and Relative Affinity"]

A --> B --> C --> D --> E --> F --> G --> H
```
