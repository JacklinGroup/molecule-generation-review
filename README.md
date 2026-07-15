# A Comprehensive Survey of Molecule Generation for De Novo Drug Design

This repository collects benchmarks, methods, code links, and toolkits related to **molecule generation for de novo drug design**, with emphasis on **pocket conditioned generation**. It serves as a companion resource for our survey paper.

If you find missing resources, please open an issue, submit a pull request, or contact us via email: jack_lin@xtu.edu.cn, siri.xu@foxmail.com

## Menu

- [Datasets](#datasets)
- [Evaluation Metrics](#evaluation-metrics)
- [Representations](#representations)
- [Methods](#methods)
  - [VAE-based](#vae-based)
  - [GAN-based](#gan-based)
  - [Flow-based](#flow-based)
  - [Diffusion-based](#diffusion-based)
  - [Pocket conditioned](#pocket-conditioned)

## Datasets

**QM9**
https://www.tensorflow.org/datasets/catalog/qm9

**ZINC-22**
https://zinc22.docking.org/

**GEOM-Drugs**
https://github.com/learningmatter-mit/geom

**CrossDocked2020**
https://github.com/gnina/models/tree/master/data/CrossDocked2020

**ChEMBL**
https://www.ebi.ac.uk/chembl/

**PubChem**
https://pubchem.ncbi.nlm.nih.gov/

**RCSB PDB**
https://www.rcsb.org/

**PDBBind**
http://www.pdbbind.org.cn/

**Binding MOAD**
http://www.bindingmoad.org/

**DrugBank**
https://go.drugbank.com/

**MOSES**
https://github.com/molecularsets/moses

## Evaluation Metrics

### Ligand-level
- Validity, Uniqueness, Novelty, FCD, SNN, Scaffold similarity

### 3D / Conformer-level
- RMSD, Coverage (COV), Matching (MAT)

### Target-specific binding
- Vina Score, Vina Min, QED, SA, Interaction Fingerprints (IFPs), Pose validity

## Representations

### Molecular
- 1D: SMILES, SELFIES, DeepSMILES, InChI
- 2D: Molecular graphs (GNN / MPNN / GAT)
- 3D: E(3)-equivariant coordinates, electron density

### Protein-Pocket
- Grid / Voxel
- Geometric graph (SE(3)-GNN / EGNN)
- Latent pocket encoding

## Methods

### VAE-based

- [2017]**GrammarVAE: Grammar Variational Autoencoder**

  Kusner M J, Paige B, Hernández-Lobato J M

  Input: 1D Seq.

  [paper](https://proceedings.mlr.press/v54/kusner17a.html) | [code](https://github.com/mkusner/grammarVAE)

- [2018]**GraphVAE: Towards Generation of Small Graphs Using Variational Autoencoders**

  Simonovsky M, Komodakis N

  Input: 2D Graph

  [paper](https://arxiv.org/abs/1802.03480) | [code](None)

- [2018]**JT-VAE: Junction Tree Variational Autoencoder for Molecular Graph Generation**

  Jin W, Barzilay R, Jaakkola T

  Input: 2D Graph

  [paper](https://proceedings.mlr.press/v80/jin18a.html) | [code](https://github.com/wengong-jin/icml18-jtnn)

- [2020]**ARAE: Adversarially Regularized Autoencoders for Molecular Design**

  Hong S, Kim D, Lim J, et al.

  Input: 1D Seq.

  [paper](None) | [code](None)

- [2020]**D-MolVAE: a variational autoencoder for molecular generation**

  Du Y, Liu X, Fu T, et al.

  Input: 2D Graph

  [paper](None) | [code](None)

- [2020]**Fragment-based VAE: A Deep Generative Model for Fragment-Based Molecule Generation**

  Podda M, Bacciu D, Micheli A

  Input: 1D Seq.

  [paper](https://doi.org/10.1007/978-3-030-50423-5_6) | [code](https://github.com/marcopodda/fragment-based-dgm)

- [2021]**RNN-Attention: Attention-based generative models for de novo molecular design**

  Dollar O, Joshi N, Beck D A, Pfaendtner J

  Input: 1D Seq.

  [paper](https://doi.org/10.1039/D1SC01050F) | [code](None)

- [2021]**TransVAE: a transformer-based variational autoencoder for molecular generation**

  Dollar O, Joshi N, Beck D A, Pfaendtner J

  Input: 1D Seq.

  [paper](https://doi.org/10.1039/D1SC01050F) | [code](https://github.com/oriondollar/TransVAE)

- [2021]**Graph Transformer VAE: Graph Transformer VAE for molecular graph generation**

  Mitton J, Hall B, Willoughby H, et al.

  Input: 2D Graph

  [paper](None) | [code](None)

- [2022]**3DLinker: an E(3)-equivariant variational autoencoder for 3D molecular linker design**

  Huang Z, Xu L, Liu Y, et al.

  Input: 3D Struct.

  [paper](https://doi.org/10.48550/arXiv.2203.10446) | [code](None)

- [2022]**Conditional β-VAE: Conditional beta-VAE reproducibility: challenges and extensions**

  Fil M, Mesinovic M, Morris M, Wildberger J

  Input: 1D Seq.

  [paper](https://doi.org/10.48550/arXiv.2112.14278) | [code](None)

- [2025]**TrustMol: trustworthy inverse molecular design via alignment with molecular dynamics**

  Wijaya K T, Ansari N, Seidel H-P, Babaei V

  Input: 1D Seq., 3D Struct.

  [paper](https://doi.org/10.1002/advs.202416356) | [code](https://github.com/ktirta/TrustMol)

### GAN-based

- [2017]**ORGAN: Sequence-Based Molecular Design with GANs**

  Guimaraes G L, Sanchez-Lengeling B, Farias P L C, Aspuru-Guzik A

  Input: 1D Seq.

  [paper](https://arxiv.org/abs/1705.10843) | [code](https://github.com/gablg1/ORGAN)

- [2018]**MolGAN: An implicit generative model for small molecular graphs**

  De Cao N, Kipf T

  Input: 2D Graph

  [paper](https://arxiv.org/abs/1805.11973) | [code](https://github.com/nicola-decao/MolGAN)

- [2022]**TransORGAN: Transformer-based Objective-reinforced Generative Adversarial Network to Generate Desired Molecules**

  Li C, Yamanishi Y, Kaitoh K, Yamanishi Y

  Input: 1D Seq.

  [paper](https://doi.org/10.24963/ijcai.2022/539) | [code](None)

- [2023]**EarlGAN: An enhanced actor-critic reinforcement learning agent-driven GAN for de novo drug design**

  Tang H, Li C, Jiang S, Yu H, Kamei S, Yamanishi Y, Morimoto Y

  Input: 1D Seq.

  [paper](https://doi.org/10.1016/j.patrec.2023.10.001) | [code](https://github.com/tang7777777/EarlGAN)

- [2023]**SpotGAN: a reverse-transformer GAN generates scaffold-constrained molecules with property optimization**

  Li C, Yamanishi Y

  Input: 1D Seq.

  [paper](https://doi.org/10.1007/978-3-031-43412-9_19) | [code](https://github.com/naruto7283/SpotGAN)

- [2023]**SpotWGAN: Wasserstein GAN for scaffold-constrained molecular generation**

  Li C, Yamanishi Y

  Input: 1D Seq.

  [paper](https://doi.org/10.1007/978-3-031-43412-9_19) | [code](https://github.com/naruto7283/SpotGAN)

- [2025]**InstGAN: Instant Actor-Critic-Driven GAN for De Novo Molecule Generation and Property Optimization**

  Tang H, Li C, Jiang S, Yu H, Kamei S, Yamanishi Y, Morimoto Y

  Input: 1D Seq.

  [paper](https://doi.org/10.24963/ijcai.2025/0694) | [code](https://github.com/tang7777777/InstGAN)

- [2025]**Range-GAN: range-aware GAN for molecular graph generation**

  Nobari A, Fazli M, Ahmadi M

  Input: 2D Graph

  [paper](None) | [code](None)

- [2025]**RL-MolGAN: reinforcement learning enhanced MolGAN for molecular generation**

  Li C, Yamanishi Y

  Input: 1D Seq.

  [paper](None) | [code](https://github.com/tang7777777/MIR)

### Flow-based

- [2020]**GraphAF: a flow-based autoregressive model for molecular graph generation**

  Shi C, Xu M, Zhu Z, Zhang W, Zhang M, Tang J

  Input: 2D Graph

  [paper](https://openreview.net/forum?id=S1esMkHYPr) | [code](https://github.com/DeepGraphLearning/GraphAF)

- [2020]**MoFlow: an invertible flow model for generating molecular graphs**

  Zang C, Wang F

  Input: 2D Graph

  [paper](https://doi.org/10.1145/3394486.3403104) | [code](https://github.com/calvin-zcx/moflow)

- [2021]**GraphDF: A Discrete Flow Model for Molecular Graph Generation**

  Luo Y, Yan K, Ji S

  Input: 2D Graph

  [paper](https://proceedings.mlr.press/v139/luo21a.html) | [code](https://github.com/divelab/DIG/tree/dig-stable/dig/ggraph/GraphDF)

- [2021]**GraphCNF: Conditional Flow Models for Graph Generation**

  Lippe P, Gavves E

  Input: 2D Graph

  [paper](https://arxiv.org/abs/1905.13108) | [code](https://github.com/lrjconan/GRF)

- [2024]**GeoBFN: unified generative modeling of 3D molecules with Bayesian flow networks**

  Song Y, Gong J, Zhou H, Zheng M, Liu J, Ma W-Y

  Input: 3D Struct.

  [paper](https://openreview.net/forum?id=PLKRH4X8M2) | [code](https://github.com/AlgoMole/GeoBFN)

- [2024]**FlowMol: mixed continuous and categorical flow matching for 3D de novo molecule generation**

  Dunn I, Koes D R

  Input: 2D Graph, 3D Struct.

  [paper](https://doi.org/10.48550/arXiv.2404.19739) | [code](https://github.com/dunni3/FlowMol)

- [2025]**GGFlow: graph-guided flow matching for molecular generation**

  Hou X, et al.

  Input: 2D Graph

  [paper](None) | [code](https://github.com/Xiaoyang878/GGFlow)

- [2025]**SemlaFlow: efficient 3D molecular generation with latent attention and equivariant flow matching**

  Irwin R, Tibo A, Janet J P, Olsson S

  Input: 2D Graph, 3D Struct.

  [paper](https://doi.org/10.48550/arXiv.2406.07266) | [code](https://github.com/rssrwn/semla-flow)

- [2026]**Megalodon-flow: modular flow matching for 3D molecular generation**

  Reidenbach D, et al.

  Input: 2D Graph, 3D Struct.

  [paper](None) | [code](https://github.com/NVIDIA-Digital-Bio/megalodon)

### Diffusion-based

- [2022]**GDSS: Score-based Generative Modeling of Graphs via the System of Stochastic Differential Equations**

  Jo J, Lee S, Hwang S J

  Input: 2D Graph

  [paper](https://proceedings.mlr.press/v162/jo22a.html) | [code](https://github.com/harryjo97/GDSS)

- [2022]**EDM: equivariant diffusion for molecule generation in 3D**

  Hoogeboom E, Satorras V G, Vignac C, Welling M

  Input: 3D Struct.

  [paper](https://proceedings.mlr.press/v162/hoogeboom22a.html) | [code](https://github.com/ehoogeboom/e3_diffusion_for_molecules)

- [2023]**D2L-OMP: diffusion-based 2D ligand generation with OMP**

  Guo H, et al.

  Input: 2D Graph

  [paper](None) | [code](None)

- [2023]**DiGress: Discrete Denoising diffusion for graph generation**

  Vignac C, Frossard P, Thiran J-P

  Input: 2D Graph

  [paper](https://doi.org/10.48550/arxiv.2209.14734) | [code](https://github.com/cvignac/DiGress)

- [2023]**MDM: Molecular Diffusion Model for 3D Molecule Generation**

  Huang W, Jing H, Liu Y, et al.

  Input: 3D Struct.

  [paper](https://arxiv.org/abs/2309.07906) | [code](https://github.com/tencent-ailab/MDM)

- [2023]**MiDi: mixed graph and 3D denoising diffusion for molecule generation**

  Vignac C, Osman N, Toni L, Frossard P

  Input: 2D Graph, 3D Struct.

  [paper](https://doi.org/10.1007/978-3-031-43415-0_33) | [code](https://github.com/cvignac/MiDi)

- [2023]**MUDiff: unified diffusion for complete molecule generation**

  Hua C, Luan S, Xu M, Ying Z, Fu J, Ermon S, Precup D

  Input: 2D Graph, 3D Struct.

  [paper](https://proceedings.mlr.press/v231/hua24a.html) | [code](https://github.com/WillHua127/mudiff)

- [2023]**TargetDiff: 3D equivariant diffusion for target-aware molecule generation and affinity prediction**

  Guan J, Qian W W, Peng X, Su Y, Peng J, Ma J

  Input: 3D Struct.

  [paper](https://openreview.net/forum?id=2f1sMgtGr5) | [code](https://github.com/guanjq/targetdiff)

- [2023]**VoxMol: 3D molecule generation by denoising voxel grids**

  Pinheiro P O, Rackers J, Kleinhenz J, et al.

  Input: 3D Struct.

  [paper](https://proceedings.neurips.cc/) | [code](https://github.com/Genentech/voxmol)

- [2024]**DiffLinker: equivariant 3D-conditional diffusion model for molecular linker design**

  Igashov I, Schneuing A, Harris C, et al.

  Input: 3D Struct.

  [paper](https://doi.org/10.1038/s43588-023-00636-7) | [code](https://github.com/igashov/DiffLinker)

- [2024]**END: equivariant neural diffusion for 3D molecule generation**

  Cornet A, et al.

  Input: 3D Struct.

  [paper](None) | [code](https://github.com/frcnt/equivariant-neural-diffusion)

- [2024]**Twigs: diffusion for 3D molecular generation**

  Mercatali G, et al.

  Input: 3D Struct.

  [paper](None) | [code](https://github.com/Aalto-QuML/Diffusion_twigs)

- [2025]**3D-EDiffMG: equivariant diffusion for 3D molecular graph generation**

  Xu Z, et al.

  Input: 2D Graph, 3D Struct.

  [paper](None) | [code](https://github.com/ZheLi-Lab-Collaboration/3D-EDiffMG)

- [2025]**ADiT: all-atom diffusion transformer for 3D molecule generation**

  Joshi R, et al.

  Input: 3D Struct.

  [paper](None) | [code](https://github.com/facebookresearch/all-atom-diffusion-transformer)

- [2025]**MDRL: molecular diffusion with reinforcement learning**

  Yuan H, et al.

  Input: 3D Struct.

  [paper](None) | [code](https://github.com/Xinol1024/MDRL)

- [2026]**TED: bridging 2D topology and 3D geometry via transformer-enhanced diffusion**

  Lu Y, Zhang J, Zhang Q, Zhang C, Zhang J

  Input: 2D Graph, 3D Struct.

  [paper](https://doi.org/10.1016/j.bspc.2025.109101) | [code](https://github.com/BaruaBee/TED)

### Pocket conditioned

- [2023]**TargetDiff: 3D equivariant diffusion for target-aware molecule generation and affinity prediction**

  Guan J, Qian W W, Peng X, Su Y, Peng J, Ma J

  [paper](https://openreview.net/forum?id=2f1sMgtGr5) | [code](https://github.com/guanjq/targetdiff)

- [2023]**D3FG: Functional-Group-Based Diffusion for Pocket-Specific Molecule Generation and Elaboration**

  Lin H, Huang Y, Zhang O, Wu L, Li S, Chen Z, Li S Z

  [paper](https://arxiv.org/abs/2306.13769) | [code](https://github.com/BIRD-TAO/D3FG)

- [2024]**DecompDiff: Diffusion Models with Decomposed Priors for Structure-Based Drug Design**

  Guan J, et al.

  [paper](https://proceedings.mlr.press/v202/guan23a.html) | [code](https://github.com/bytedance/DecompDiff)

- [2024]**IPDiff: protein-ligand interaction prior for binding-aware 3D molecule diffusion**

  Huang Z, Yang L, Zhou X, et al.

  [paper](None) | [code](https://github.com/YangLing0818/IPDiff)

- [2024]**TAGMol**

  Dorna V, et al.

  [paper](None) | [code](None)

- [2024]**ALiDiff: Aligning Target-Aware Molecule Diffusion Models with Exact Energy Optimization**

  Gu S, et al.

  [paper](https://arxiv.org/abs/2407.01648) | [code](https://github.com/MinkaiXu/AliDiff)

- [2024]**BindDM: Binding-Adaptive Diffusion Models for Structure-Based Drug Design**

  Huang Z, Yang L, Zhang Z, Zhou X, Bao Y, Zheng X, Yang Y, Wang Y, Yang W

  [paper](https://ojs.aaai.org/index.php/AAAI/article/view/29162) | [code](https://github.com/YangLing0818/BindDM)

- [2024]**DiffSBDD: structure-based drug design with equivariant diffusion models**

  Schneuing A, Harris C, Du Y, et al.

  [paper](https://doi.org/10.1038/s43588-024-00737-x) | [code](https://github.com/arneschneuing/DiffSBDD)

- [2024]**VoxBind**

  Pinheiro P O, et al.

  [paper](None) | [code](None)

- [2024]**PMDM**

  Huang L, et al.

  [paper](None) | [code](None)

- [2024]**GCDM**

  Morehead A, et al.

  [paper](None) | [code](None)

- [2024]**KGDiff**

  Qian H, et al.

  [paper](None) | [code](None)

- [2024]**FlowSBDD**

  Zhang et al.

  [paper](None) | [code](None)

- [2024]**MolCRAFT: Structure-Based Drug Design in Continuous Parameter Space**

  Qu Y, Qiu K, Song Y, Gong J, Han J, Zheng M, Zhou H, Ma W-Y

  [paper](https://arxiv.org/abs/2404.12141) | [code](https://github.com/AlgoMole/MolCRAFT)

- [2024]**PocketFlow**

  Jiang Y, et al.

  [paper](None) | [code](None)

- [2024]**FlexSBDD: Structure-Based Drug Design with Flexible Protein Modeling**

  Zhang Z, et al.

  [paper](None) | [code](https://github.com/zaixizhang/FlexSBDD)

- [2025]**DiffGui**

  Hu et al.

  [paper](None) | [code](None)

- [2025]**SGEDiff**

  Gong et al.

  [paper](None) | [code](None)

- [2025]**MSIDiff**

  Zhang et al.

  [paper](None) | [code](None)

- [2025]**BoKDiff**

  Yalabadi et al.

  [paper](None) | [code](None)

- [2025]**PAFlow: Prior-Guided Flow Matching for Target-Aware Molecule Design with Learnable Atom Number**

  Zhou J, Qian H, Tu S, Xu L

  [paper](https://arxiv.org/abs/2509.01486) | [code](None)

- [2025]**MolFORM: Multi-modal Flow Matching for Structure-Based Drug Design**

  Huang et al.

  [paper](https://arxiv.org/abs/2507.05503) | [code](https://github.com/daiheng-zhang/SBDD-MolFORM)
