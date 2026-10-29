# Machine Learning Portfolio

This repository collects coursework notebooks and small machine learning projects. The projects below are the best starting points for reviewing my implementation work; the course notebooks are retained as learning materials.

## Featured work

| Project | Focus | Current state |
| --- | --- | --- |
| [Linear SVM from scratch](ThesisStudy/SVMReadMe.md) | NumPy implementation of a linear soft-margin classifier, with a synthetic-data visualization and a scikit-learn comparison | Educational prototype; evaluation is currently on the training sample only |
| [CNN and depthwise separable convolution](CNNvsMobileNet.md) | Compare a standard convolution block with a depthwise-separable block | Model blocks are implemented; a controlled benchmark and measured results are still needed |
| [SimCLR on STL-10](day03_2_student_v1_3.ipynb) | Self-supervised image representation learning with two augmented views, a ResNet-18 encoder, and NT-Xent loss | The three `day03_*` notebooks form one project sequence; Colab-oriented experiment that still needs a clearly documented end-to-end run and results |

## Other projects and learning notebooks

- [Stock price LSTM](LSTMpredict/StockPrediction.md): univariate Samsung Electronics price forecasting.
- [GAN on MNIST](ThesisStudy/GANREADME.md): a small vanilla GAN implementation.
- [Mixed-corpus tokenizer](day02_01_text_data_tokenizer_v1_1.ipynb) and [MiniGPT lab](day02_lab_minigpt_student_v2_1.ipynb): language-model course exercises.
- **SimCLR project sequence (`day03_*`)**:
  - [Vision foundations](day03_0_vision_pytorch_basic_student_v1_2.ipynb): PyTorch image handling, transforms, CNNs, and pretrained ResNet foundations used by SimCLR.
  - [STL-10 data and evaluation protocol](day03_1_STD10_pipeline_student.ipynb): dataset inspection and the project’s evaluation setup.
  - [SimCLR model and experiments](day03_2_student_v1_3.ipynb): two-view augmentations, encoder/projector, NT-Xent, and experiment code.
- [Multivariable stock notebook](LSTMpredict/MultiVariable.ipynb): an unfinished experiment; its current saved notebook contains a column mismatch error.

## Reproducibility and interpretation

Most notebooks were authored for Google Colab and may download datasets or pretrained weights at runtime. Check each notebook's setup cells and data source before running. Saved notebook outputs are illustrative and are not a substitute for rerunning the code in a documented environment.

These projects are learning prototypes, not claims of validated research results. For a research-ready presentation, each experiment needs a clear question, data split, baseline, metrics, reproducible settings, results, and limitations. Financial forecasting in particular requires time-ordered validation and preprocessing fitted only on training data.

## Repository map

- `ThesisStudy/`: SVM and GAN learning projects.
- `LSTMpredict/`: univariate and multivariable time-series experiments.
- `day02_*`: tokenizer and MiniGPT exercises.
- `day03_*`: computer-vision and SimCLR exercises.

## Suggested review order

1. Read the project overview and limitations above.
2. Start with the SVM notebook for the smallest self-contained implementation.
3. Review the CNN/MobileNet comparison after benchmark results are added.
4. Read the three `day03_*` notebooks together as one larger, environment-dependent SimCLR project.
