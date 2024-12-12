# Bootstrapping Language-Guided Navigation Learning with Self-Refining Data Flywheel

[![arXiv](https://img.shields.io/badge/arXiv-2412.08467-b31b1b.svg)](https://arxiv.org/abs/2412.08467)   

#### [Zun Wang](https://zunwang1.github.io/), [Jialu Li](https://jialuli-luka.github.io/), [Yicong Hong](http://www.yiconghong.me/), [Songze Li](https://scholar.google.com/citations?user=8rBMUD4AAAAJ), [Kunchang Li](https://andy1621.github.io/), [Shoubin Yu](https://yui010206.github.io/), [Yi Wang](https://shepnerd.github.io/), [Yu Qiao](https://scholar.google.com/citations?hl=en&user=gFtI-8QAAAAJ), [Yali Wang](https://scholar.google.com/citations?user=hD948dkAAAAJ),  [Mohit Bansal](https://www.cs.unc.edu/~mbansal/), [Limin Wang](https://wanglimin.github.io/)

<br>
<img width="950" src="files/teaser.png"/>
<br>


#### Code coming soon!

## ToDos
- [ ] Release the code, data, and models for training navigators.
- [ ] Release the code, data, and models for training generators.
- [ ] Release the code for data generation.

## Installation

1. Install Matterport3D simulators: follow instructions [here](https://github.com/peteanderson80/Matterport3DSimulator). We use the latest version instead of v0.1.
```
export PYTHONPATH=Matterport3DSimulator/build:$PYTHONPATH
```

2. Install requirements:
```
conda create --name vlnde python=3.9
conda activate vlnde
pip install -r requirements.txt
```

## Reproduce Testing Results
### R2R Navigation
```
cd VLN-DUET/map_nav_src
bash scripts/valid_r2r.bash
```
Log:
```
Env name: val_train_seen, action_steps: 5.36, steps: 5.81, lengths: 11.80, nav_error: 1.00, oracle_error: 0.56, sr: 91.33, oracle_sr: 94.00, spl: 87.94, nDTW: 89.56, SDTW: 86.45, CLS: 88.58

Env name: val_seen, action_steps: 5.30, steps: 5.57, lengths: 11.21, nav_error: 1.54, oracle_error: 0.95, sr: 86.78, oracle_sr: 90.70, spl: 83.31, nDTW: 86.67, SDTW: 81.03, CLS: 85.26

Env name: val_unseen, action_steps: 5.63, steps: 6.22, lengths: 12.00, nav_error: 1.62, oracle_error: 0.92, sr: 85.65, oracle_sr: 90.34, spl: 78.72, nDTW: 81.13, SDTW: 75.73, CLS: 79.85
```

### R2R Instruction Generation
```
cd Mantis
bash mantis/train/scripts/valid_best.bash
```
Log:
```
bleu1: 75.32, bleu4: 31.14, meteor: 24.99, rouge: 51.37, cider: 49.16, spice: 26.18, spice_v1: 30.94, num_words: 198.00, avg_lens: 23.78
```

# Citation

If you find our project useful in your research, please cite the following paper:

```bibtex
@article{zun2024srdf,
    author = { Wang, Zun and  Li, Jialu and Hong, Yicong and Li, Songze and Li, Kunchang and Yu, Shoubin and Wang, Yi and Qiao, Yu and Wang, Yali and Bansal, Mohit and Wang, Limin},
    title  = {Bootstrapping Language-Guided Navigation Learning with Self-Refining Data Flywheel},
	journal   = {arxiv},
	year      = {2024},
	url       = {https://arxiv.org/abs/2412.08467}
}
```
