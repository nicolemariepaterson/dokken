

##  <h1 align="center">Molecular Docking Pipeline for Predicting Influenza Host Shifts</h1>


<p align="center">
  <img src="DOKKEN.png" 
       alt="DOKKEN!!!"
       width="800"/>
</p>

<h1 align="center"></h1>
Guided molecular docking pipeline with automated bounding box generation feature and ranked pose filtering by convoluted neural network. 

## <h1 align="center">Pipeline Workflow </h1>

```mermaid
flowchart TB

    %% Large vertical layout

    A[" 
    Receptor Prediction
    ----------------------------------------
    Predict Receptor Structure
    OpenFold3
    "]

    B[" 
    Identify Interface (prior)
    ----------------------------------------
    Machine Learning Model
    PyTorch Implementation
    "]

    C[" 
    Side chain optimization
    ----------------------------------------
    Side-Chain Optimization
    Flexible Residues from Prior
    "]

    D[" 
    Bounding Box Generation
    ----------------------------------------
    Bounding Box Generation
    Flexible Residue Selection
    "]

    E[" 
    Vina/Smina Ligand Docking
    ----------------------------------------
    Vina Docking
    Constrained Search Space
    "]

    F[" 
    Voxelization for Pose Filter
    ----------------------------------------
    Voxelization
    Optional Interface Prior Channel
    "]

    G[" 
    Pose Ranking using CNN
    ----------------------------------------
    CNN Scoring
    Pose Ranking
    "]

    H[" 
    Comparison and Results
    ----------------------------------------
    Select Top Poses
    Relative Affinity Comparison
    "]

    A --> B --> C --> D --> E --> F --> G --> H

    %% Styling
    classDef big fill:#F0F7FF,stroke:#1565C0,stroke-width:4px,color:#0B3C5D;
    class A,B,C,D,E,F,G,H big;

    linkStyle default stroke-width:3px
```

