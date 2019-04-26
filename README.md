# Model-Agnostic Meta-Learning on Omniglot, miniImageNet, and CIFAR-FS

This repo extends the original MAML code ([link](https://github.com/cbfinn/maml), [ICML 2017 paper](https://arxiv.org/abs/1703.03400)) [1] with **CIFAR-FS** (CIFAR few shot) classification based on the splits in Luca et al. [2]. It includes code for running the few-shot supervised learning domain experiments, including sinusoid regression, Omniglot classification, MiniImagenet classification, and the newly added CIFAR-FS classification.

For the experiments in the RL domain, see [this codebase](https://github.com/cbfinn/maml_rl).

A report detailing the implementation details and reproducibility can be found [here](https://openreview.net/forum?id=BJx0N2I6IN).

### Dependencies
This code requires the following:
* python 2.\* or python 3.\*
* TensorFlow v1.0+

These results were achieved using TensorFlow-gpu 1.8.0, CUDA 9.0 and cudnn 7.

### Data
For the Omniglot, MiniImagenet and CIFAR-FS data, see the usage instructions in `data/omniglot_resized/resize_images.py` and `data/miniImagenet/proc_images.py` and `data/CIFARFS/get_cifarfs.py` respectively.

### Usage
To run the code, see the usage instructions at the top of `main.py`.

### Results

After 60,000 iterations, with a 95% confidence interval, and 10 finetune steps:

| Dataset, method | this code<br />accuracy | reported by<br />MAML [1] & R2D2 [2] |
| ------------- | :---------------------: | :-----------: |
| CIFAR-FS, MAML 5-way, 1-shot |      56.8 ± 1.9%       | 58.9 ± 1.9% |
| CIFAR-FS, MAML 5-way, 5-shot | 70.8 ± 0.9% | 71.5 ± 1.0% |
| CIFAR-FS, MAML 2-way, 1-shot | 83.1 ± 2.6% | 82.8 ± 2.7% |
| CIFAR-FS, MAML 2-way, 5-shot | 88.5 ± 1.1% | 88.3 ± 1.1% |
| miniImagenet, MAML 5-way, 1-shot | 47.6 ± 1.9% | 48.7 ± 1.8% |
| miniImagenet, MAML 5-way, 5-shot | 63.0 ± 0.9% | 63.1 ± 0.9% |
| miniImagenet, MAML 2-way, 1-shot | 78.8 ± 2.8% | 74.9 ± 3.0% |
| miniImagenet, MAML 2-way, 5-shot | 82.6 ± 1.2% | 84.4 ± 1.2% |

![alt text](https://i.ibb.co/nc49m4c/Screen-Shot-2019-04-26-at-14-22-45.png)

### Cite this work
If you use (part of) this code or work, please cite the following work:
```
@article{devosreproducing,
  title={Reproducing Meta-learning with differentiable closed-form solvers},
  author={Devos, Arnout and Chatel, Sylvain and Grossglauser, Matthias},
  booktitle={International Conference on Learning Representations},
  year={2019},
  url={https://openreview.net/forum?id=BJx0N2I6IN},
}
```
### References

[1] Finn, Chelsea, Pieter Abbeel, and Sergey Levine. "Model-agnostic meta-learning for fast adaptation of deep networks." *arXiv preprint arXiv:1703.03400* (2017).

[2] Bertinetto, Luca, et al. "Meta-learning with differentiable closed-form solvers." *arXiv preprint arXiv:1805.08136* (2018).
