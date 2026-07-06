# A Comprehensive Survey of Molecule Generation for De Novo Drug Design

This repository collects benchmarks, methods, code links, and toolkits related to **molecule generation for de novo drug design**, with emphasis on **pocket conditioned generation**. It serves as a companion resource for our survey paper.

If you find missing resources, please open an issue, submit a pull request, or contact us via email: jack_lin@xtu.edu.cn

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
- [Platform and Toolkit](#platform-and-toolkit)

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

**Durian**
https://github.com/ninglab/Durian

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

- [2018]**Junction Tree Variational Autoencoder for Molecular Graph Generation**

  Jin W, Barzilay R, Jaakkola T

  [paper](https://proceedings.mlr.press/v80/jin18a.html) | [code](https://github.com/wengong-jin/icml18-jtnn)

- [2020]**VAE-Sim: a novel molecular similarity measure based on a variational autoencoder**

  Samanta S, O'Hagan S, Swainston N, Roberts T J, Kell D B

  [paper](https://doi.org/10.3390/molecules25153446) | [code](None)

- [2020]**Re-balancing variational autoencoder loss for molecule sequence generation**

  Yan C, Wang S, Yang J, Xu T, Huang J

  [paper](https://doi.org/10.1145/3388440.3412458) | [code](None)

- [2021]**Attention-based generative models for de novo molecular design**

  Dollar O, Joshi N, Beck D A, Pfaendtner J

  [paper](https://doi.org/10.1039/D1SC01050F) | [code](None)

- [2021]**Conditional beta-VAE reproducibility: challenges and extensions**

  Fil M, Mesinovic M, Morris M, Wildberger J

  [paper](https://doi.org/10.48550/arXiv.2112.14278) | [code](None)

- [2021]**GF-VAE: a flow-based variational autoencoder for molecule generation**

  Ma C, Zhang X

  [paper](https://doi.org/10.1145/3459637.3482260) | [code](None)

- [2023]**Pretrained JT-VAE for HOMO value prediction and molecular optimization**

  Kondratyev V, Dryzhakov M, Gimadiev T, Slutskiy D

  [paper](https://doi.org/10.1186/s13321-023-00681-4) | [code](https://github.com/VldKnd/vae_qm9)

- [2023]**Cage-VAE: deep generative design of porous organic cages**

  Zhou J, Mroz A, Jelfs K E

  [paper](https://doi.org/10.1039/D3DD00154G) | [code](https://github.com/JiajunZhou96/Cage-VAE)

- [2024]**Transformer VAE for unseen structure generation**

  Yoshikai Y, Mizuno T, Nemoto S, Kusuhara H

  [paper](https://doi.org/10.48550/arXiv.2402.11950) | [code](https://github.com/mizuno-group/TransformerVAE)

- [2025]**TrustMol: trustworthy inverse molecular design via alignment with molecular dynamics**

  Wijaya K T, Ansari N, Seidel H-P, Babaei V

  [paper](https://doi.org/10.1002/advs.202416356) | [code](https://github.com/ktirta/TrustMol)

- [2025]**Adaptive beta-VAE for optimized organic fluorophore search**

  Xu Y, Luo Y, Li B, et al.

  [paper](https://doi.org/10.1021/jacsau.5c00052) | [code](https://codeocean.com/capsule/7686798/tree/v1)

### GAN-based

- [2020]**Mol-CycleGAN: a generative model for molecular optimization**

  Maziarka L, Pocha A, Kaczmarczyk J, Rataj K, Danel T, Warchol M

  [paper](https://doi.org/10.1186/s13321-019-0404-1) | [code](None)

- [2021]**LA-CycleGAN: improving de novo molecule generation by embedding LSTM and attention in CycleGAN**

  Wang F, Feng X, Guo X, Xu L, Xie L, Chang S

  [paper](https://doi.org/10.3389/fgene.2021.709500) | [code](https://osf.io/42x7d/?view_only=e2cf708215894283896576189928509e)

- [2022]**ED-GAN: a pocket-based 3D molecule generative model fueled by experimental electron density**

  Wang L, Bai R, Shi X, Zhang W, et al.

  [paper](https://doi.org/10.1038/s41598-022-19363-6) | [code](https://edmg.stonewise.cn/#/create)

- [2023]**SpotGAN: a reverse-transformer GAN generates scaffold-constrained molecules with property optimization**

  Li C, Yamanishi Y

  [paper](https://doi.org/10.1007/978-3-031-43412-9_19) | [code](None)

- [2024]**MedGAN: optimized GAN with graph convolutional networks for novel molecule design**

  Macedo B, Ribeiro Vaz I, Taveira Gomes T

  [paper](https://doi.org/10.1038/s41598-023-50834-6) | [code](https://github.com/bmacedo111/MedGAN/)

- [2024]**TenGAN: pure transformer encoders make an efficient discrete GAN for de novo molecular generation**

  Li C, Yamanishi Y

  [paper](https://proceedings.mlr.press/v238/li24a.html) | [code](https://github.com/chenli1536/TenGAN)

- [2025]**TopMT-GAN: a 3D topology-driven generative model for structure-based ligand design**

  Wang S, Lin T, Peng T, Xing E, Chen S, Kara L B, Cheng X

  [paper](https://doi.org/10.1039/D4SC05211K) | [code](https://github.com/aeghnsw/TopMT)

### Flow-based

- [2020]**GraphAF: a flow-based autoregressive model for molecular graph generation**

  Shi C, Xu M, Zhu Z, Zhang W, Zhang M, Tang J

  [paper](https://openreview.net/forum?id=S1esMkHYPr) | [code](https://github.com/DeepGraphLearning/GraphAF)

- [2020]**MoFlow: an invertible flow model for generating molecular graphs**

  Zang C, Wang F

  [paper](https://doi.org/10.1145/3394486.3403104) | [code](https://github.com/calvin-zcx/moflow)

- [2024]**GeoBFN: unified generative modeling of 3D molecules with Bayesian flow networks**

  Song Y, Gong J, Zhou H, Zheng M, Liu J, Ma W-Y

  [paper](https://openreview.net/forum?id=) | [code](https://github.com/AlgoMole/GeoBFN)

- [2024]**FlowMol: mixed continuous and categorical flow matching for 3D de novo molecule generation**

  Dunn I, Koes D R

  [paper](https://doi.org/10.48550/arXiv.2404.19739) | [code](https://github.com/dunni3/FlowMol)

- [2024]**FlowMol-CTMC: exploring discrete flow matching for 3D de novo molecule generation**

  Dunn I, Koes D R

  [paper](https://doi.org/10.48550/arXiv.2411.16644) | [code](https://github.com/dunni3/FlowMol)

- [2024]**SemlaFlow: efficient 3D molecular generation with latent attention and equivariant flow matching**

  Irwin R, Tibo A, Janet J P, Olsson S

  [paper](https://doi.org/10.48550/arXiv.2406.07266) | [code](None)

- [2025]**VNFlow: integration of variational autoencoders and normalizing flows for novel molecular design**

  Hostas J, Ghaemi M S, Hu H, Lin J, Hu A, Ooi H K

  [paper](https://doi.org/10.1186/s13321-025-01104-2) | [code](https://github.com/nrc-cnrc/VNFlow)

- [2025]**EnFlow: energy-guided flow matching for conformer generation**

  Xu G, Yi X, Zhao P, Bian Y

  [paper](https://doi.org/10.48550/arXiv.2512.22597) | [code](https://github.com/Rich-XGK/EnFlow.git)

### Diffusion-based

- [2022]**EDM: equivariant diffusion for molecule generation in 3D**

  Hoogeboom E, Satorras V G, Vignac C, Welling M

  [paper](https://proceedings.mlr.press/v162/hoogeboom22a.html) | [code](https://github.com/ehoogeboom/e3_diffusion_for_molecules)

- [2022]**GeoDiff: a geometric diffusion model for molecular conformation generation**

  Xu M, Yu L, Song Y, Shi C, Ermon S, Tang J

  [paper](https://openreview.net/forum?id=PzcvxEMzvQC) | [code](https://github.com/MinkaiXu/GeoDiff)

- [2023]**TargetDiff: 3D equivariant diffusion for target-aware molecule generation and affinity prediction**

  Guan J, Qian W W, Peng X, Su Y, Peng J, Ma J

  [paper](https://openreview.net/forum?id=) | [code](https://github.com/guanjq/targetdiff)

- [2023]**EQGAT-diff: navigating the design space of equivariant diffusion-based generative models**

  Le T, Cremer J, Noe F, Clevert D-A, Schutt K

  [paper](https://doi.org/10.48550/arXiv.2309.17296) | [code](https://github.com/jule-c/eqgat_diff)

- [2023]**MiDi: mixed graph and 3D denoising diffusion for molecule generation**

  Vignac C, Osman N, Toni L, Frossard P

  [paper](https://doi.org/10.1007/978-3-031-43415-0_33) | [code](https://github.com/cvignac/MiDi)

- [2023]**VoxMol: 3D molecule generation by denoising voxel grids**

  Pinheiro P O, Rackers J, Kleinhenz J, et al.

  [paper](https://proceedings.neurips.cc/) | [code](None)

- [2024]**MUDiff: unified diffusion for complete molecule generation**

  Hua C, Luan S, Xu M, Ying Z, Fu J, Ermon S, Precup D

  [paper](https://proceedings.mlr.press/v231/hua24a.html) | [code](https://github.com/WillHua127/mudiff)

- [2024]**KGDiff: towards explainable target-aware molecule generation with knowledge guidance**

  Qian H, Huang W, Tu S, Xu L

  [paper](https://doi.org/10.1093/bib/bbad435) | [code](https://github.com/CMACH508/KGDiff)

- [2024]**IPDiff: protein-ligand interaction prior for binding-aware 3D molecule diffusion models**

  Huang Z, Yang L, Zhou X, Zhang Z, Zhang W, Zheng X, Chen J, Wang Y, Cui B, Yang W

  [paper](https://openreview.net/forum?id=) | [code](https://github.com/YangLing0818/IPDiff)

- [2024]**DiffSBDD: structure-based drug design with equivariant diffusion models**

  Schneuing A, Harris C, Du Y, Didi K, Jamasb A, Igashov I, Du W, Gomes C, Blundell T L, Lio P, et al.

  [paper](https://doi.org/10.1038/s43588-024-00737-x) | [code](https://github.com/arneschneuing/DiffSBDD)

- [2025]**DiffBP: generative diffusion of 3D molecules for target protein binding**

  Lin H, Huang Y, Zhang O, Ma S, Liu M, Li X, Wu L, Wang J, Hou T, Li S Z

  [paper](https://doi.org/10.1039/D4SC05894A) | [code](https://drive.google.com/drive/folders/1bSDoQBERjXXvwAFRscu)

- [2025]**PGDiff: a physics-guided equivariant diffusion model for structure-based drug design**

  Nan X, Liu X, You X, Du Y, Ji C, Song J

  [paper](https://doi.org/10.1109/BIBM66473.2025.11357162) | [code](https://anonymous.4open.science/r/PGDiff-25B5/)

- [2025]**BInD: bond and interaction-generating diffusion model for multi-objective structure-based drug design**

  Lee J, Zhung W, Seo J, Kim W Y

  [paper](https://doi.org/10.1002/advs.202502702) | [code](https://github.com/lee-jwon/BInD)

- [2026]**MSIDiff: multi-stage interaction-aware diffusion model for protein-specific 3D molecule generation**

  Zhang Y, Ma J, Zhang Z, Dong Z, Wang S

  [paper](https://doi.org/10.1016/j.eswa.2025.129820) | [code](https://github.com/zhangyaoxiang/MSIDiff)

- [2026]**TED: bridging 2D topology and 3D geometry via transformer-enhanced diffusion**

  Lu Y, Zhang J, Zhang Q, Zhang C, Zhang J

  [paper](https://doi.org/10.1016/j.bspc.2025.109101) | [code](https://github.com/Bar_uaBee/TED)

### Pocket conditioned

- [2021]**Pocket2Mol: a 3D generative model for structure-based drug design**

  Luo S, Guan J, Ma J, Peng J

  [paper](https://proceedings.neurips.cc/paper/2021/hash/5f267a42f1e8f8e486a0e09a4133f880-Abstract.html) | [code](https://github.com/pengxingang/Pocket2Mol)

- [2022]**Generating 3D molecules conditional on receptor binding sites with deep generative models**

  Ragoza M, Masuda T, Koes D R

  [paper](https://doi.org/10.1039/D1SC05976A) | [code](None)

- [2023]**TargetDiff: 3D equivariant diffusion for target-aware molecule generation**

  Guan J, Qian W W, Peng X, Su Y, Peng J, Ma J

  [paper](https://openreview.net/forum?id=) | [code](https://github.com/guanjq/targetdiff)

- [2024]**IPDiff: protein-ligand interaction prior for binding-aware 3D molecule diffusion**

  Huang Z, Yang L, Zhou X, et al.

  [paper](https://openreview.net/forum?id=) | [code](https://github.com/YangLing0818/IPDiff)

- [2024]**DiffSBDD: structure-based drug design with equivariant diffusion models**

  Schneuing A, Harris C, Du Y, et al.

  [paper](https://doi.org/10.1038/s43588-024-00737-x) | [code](https://github.com/arneschneuing/DiffSBDD)

- [2024]**PIDiff: physics informed diffusion model for protein pocket-specific 3D molecular generation**

  Choi S, Seo S, Kim B J, Park C, Park S

  [paper](https://doi.org/10.1016/j.compbiomed.2024.108865) | [code](None)

- [2025]**DiffBP: generative diffusion of 3D molecules for target protein binding**

  Lin H, Huang Y, Zhang O, et al.

  [paper](https://doi.org/10.1039/D4SC05894A) | [code](https://drive.google.com/drive/folders/1bSDoQBERjXXvwAFRscu)

- [2025]**BInD: bond and interaction-generating diffusion model for multi-objective SBDD**

  Lee J, Zhung W, Seo J, Kim W Y

  [paper](https://doi.org/10.1002/advs.202502702) | [code](https://github.com/lee-jwon/BInD)

- [2025]**AlphaDrug: protein target specific de novo molecular generation**

  Qian H, Lin C, Zhao D, Tu S, Xu L

  [paper](https://doi.org/10.1093/pnasnexus/pgac227) | [code](None)

- [2025]**Guided equivariant diffusion for target-aware 3D molecular generation**

  Hu Q, Sun C, He H, Xu J, Liu D, Zhang W, Shi S, Zhang K, Li H

  [paper](https://doi.org/10.1038/s41467-025-63245-0) | [code](None)

## Platform and Toolkit

- [RDKit](https://www.rdkit.org/)
- [OpenBabel](https://openbabel.org/)
- [DeepChem](https://deepchem.io/)
- [TorchDrug](https://torchdrug.ai/)
- [DGL-LifeSci](https://github.com/awslabs/dgl-lifesci)
- [PaddleHelix](https://github.com/PaddlePaddle/PaddleHelix)
- [AutoDock Vina](https://vina.scripps.edu/)
- [REINVENT](https://github.com/MolecularAI/REINVENT4)
- [PoseBusters](https://github.com/maabuu/posebusters)
