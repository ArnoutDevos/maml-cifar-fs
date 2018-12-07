# Model-Agnostic Meta-Learning on Omniglot, miniImageNet, and CIFAR-FS

This repo extends the original MAML code ([link](https://github.com/cbfinn/maml), [ICML 2017 paper](https://arxiv.org/abs/1703.03400)) [1] with CIFAR-FS classification based on the splits in Luca et al. [2]. It includes code for running the few-shot supervised learning domain experiments, including sinusoid regression, Omniglot classification, MiniImagenet classification, and the newly added CIFAR-FS classification.

For the experiments in the RL domain, see [this codebase](https://github.com/cbfinn/maml_rl).

### Dependencies
This code requires the following:
* python 2.\* or python 3.\*
* TensorFlow v1.0+

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
| CIFAR-FS, MAML 2-way, 1-shot | - | 82.8 ± 2.7% |
| CIFAR-FS, MAML 2-way, 5-shot | - | 88.3 ± 1.1% |
| miniImagenet, MAML 5-way, 1-shot | 47.6 ± 1.9% | 48.7 ± 1.8% |
| miniImagenet, MAML 5-way, 5-shot | - | 63.1 ± 0.9% |
| miniImagenet, MAML 2-way, 1-shot | - | 74.9 ± 3.0% |
| miniImagenet, MAML 2-way, 5-shot | - | 84.4 ± 1.2% |

### References

[1] Finn, Chelsea, Pieter Abbeel, and Sergey Levine. "Model-agnostic meta-learning for fast adaptation of deep networks." *arXiv preprint arXiv:1703.03400* (2017).

[2] Bertinetto, Luca, et al. "Meta-learning with differentiable closed-form solvers." *arXiv preprint arXiv:1805.08136* (2018).
