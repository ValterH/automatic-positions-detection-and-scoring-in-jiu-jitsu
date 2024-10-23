# Video-Based Detection of Combat Positions and Automatic Scoring in Jiu-jitsu

This is my re-implementation of our [paper](https://dl.acm.org/doi/10.1145/3552437.3555707).

## Installation
For help please refer to the original [ViTPose repository](https://github.com/ViTAE-Transformer/ViTPose) for more details (specifically issue [#97](https://github.com/ViTAE-Transformer/ViTPose/issues/97)).
```bash
# Initialize the submodules (ViTPose and mmdetection)
git submodule update --init --recursive
conda create -n bjjtrack python=3.8
# Install PyTorch
pip install torch==1.9.0+cu111 torchvision==0.10.0+cu111 torchaudio==0.9.0 -f https://download.pytorch.org/whl/torch_stable.html
# Install mmcv
pip install mmcv-full==1.4.8 -f https://download.openmmlab.com/mmcv/dist/cu111/torch1.9.0/index.html
# Install mmdetection
pip install mmdet==2.28.2
# Install ViTPose
cd ../ViTPose
pip install -v -e .
# Install additional ViTPose dependencies
pip install timm==0.4.9 einops

# Install additional dependencies
pip install -r requirements.txt
```


## Results

**Position Classification**
| Method       | One View     | Two Views    | Three Views   |
|--------------|--------------|--------------|---------------|
| Two Person   | 0.8 ± 0.015  | 0.83 ± 0.012 | 0.84 ± 0.004  |
| Two Person*  | 0.84 ± 0.011 | 0.86 ± 0.011 | 0.87 ± 0.005  |
| Two person ★ | 0.86 ± 0.01  | 0.89 ± 0.006 | 0.92 ± 0.004  |

**Scoring Timeline**
[![Figure 6. Scoring Timeline](figures/scoring.png)](figures/scoring.png)

## Reproducing the results
TODO: Upload weights and data needed to reproduce everything.
> To reproduce the main results first run the tracking pipeline using the `run_tracking.py` script for all three angles. 

To reproduce the scoring results first run the `evaluate_scoring.py` script to generate the scoring timeline and then `reproduce_scoring_fig.py` to generate the figure.

For position classification results, run the `evaluate_positions.py` script.


## Citing
```
@inproceedings{hudovernik2022video,
  author = {Hudovernik, Valter and  Sko{\v{c}}aj, Danijel},
  title = {{Video-Based Detection of Combat Positions and Automatic Scoring in Jiu-jitsu}},
  booktitle={Proceedings of the 5th International ACM Workshop on Multimedia Content Analysis in Sports},
  pages={55--63},
  year={2022}
}
```
