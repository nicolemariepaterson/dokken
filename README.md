

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
    Predict Receptor Structure with OpenFold3
    "]

    B[" 
    Identify Interface (prior)
    ----------------------------------------
    PyTorch Implementation 
    "]

    C[" 
    Side chain optimization
    ----------------------------------------
    Side-Chain Optimization of Flexible Residues (Prior)
    "]

    D[" 
    Bounding Box Generation
    ----------------------------------------
    Bounding Box Generation, Flexible Residue Selection for Docking from Prior
    "]

    E[" 
    Vina/Smina Ligand Docking
    ----------------------------------------
    Vina/Smina Docking
    "]

    F[" 
    Voxelization for Pose Filter
    ----------------------------------------
    Voxelization before Passing to CNN
    "]

    G[" 
    Pose Ranking using CNN
    ----------------------------------------
    CNN Scoring, Pose Ranking, Filter
    "]

    H[" 
    Comparison and Results
    ----------------------------------------
    Relative Affinity Comparison top three poses
    "]

    A --> B --> C --> D --> E --> F --> G --> H

    %% Styling
    classDef big fill:#F0F7FF,stroke:#1565C0,stroke-width:4px,color:#0B3C5D;
    class A,B,C,D,E,F,G,H big;

    linkStyle default stroke-width:3px
```

