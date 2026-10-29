# Machine Learning Portfolio

This repository contains small machine learning projects and coursework notebooks. Start with the project READMEs for each project's goal, files, and current limitations.

## Projects

| Project | What it explores | Status |
| --- | --- | --- |
| [SimCLR on STL-10](projects/simclr/README.md) | Self-supervised image representation learning with contrastive views | Three related notebooks; Colab-oriented and still needs a fresh, documented end-to-end run before its results are presented as research findings |
| [CNN and depthwise separable convolution](projects/cnn-mobilenet/README.md) | Compare standard and depthwise-separable convolution blocks | Blocks are implemented; controlled benchmark results are not yet included |
| [Stock price forecasting with LSTM](projects/stock-lstm/README.md) | Univariate and multivariable Samsung Electronics price prediction | Exploratory; validation and data pipeline need further work |
| [Vanilla GAN on MNIST](projects/gan/README.md) | Fully connected GAN implementation | Notebook has a saved MNIST download failure |
| [Linear SVM from scratch](projects/svm/README.md) | NumPy implementation of a soft-margin linear classifier | Educational prototype; current comparison uses the training sample |

## Coursework

[Language modeling exercises](coursework/language-modeling/README.md) contains the tokenizer and MiniGPT notebooks. The three `day03_*` notebooks are grouped together as one SimCLR project under `projects/simclr/`.

## Reproducibility

Many notebooks were authored for Google Colab and download datasets or pretrained weights at runtime. See each project README for setup notes. Saved notebook outputs are not a substitute for rerunning the code in a documented environment.

These are learning projects, not claims of validated research results. A research-ready presentation should state the question, data split, baseline, metrics, settings, results, and limitations. Financial forecasting needs time-ordered validation and preprocessing fitted only on training data.
