# SimCLR on STL-10

This project studies self-supervised visual representation learning with SimCLR. The three `day03_*` notebooks are successive parts of the same project.

## Notebook sequence

1. [`day03_0_vision_pytorch_basic_student_v1_2.ipynb`](day03_0_vision_pytorch_basic_student_v1_2.ipynb) introduces the PyTorch image, transform, CNN, and pretrained ResNet concepts used by the project.
2. [`day03_1_STD10_pipeline_student.ipynb`](day03_1_STD10_pipeline_student.ipynb) inspects the STL-10 splits and prepares the project data/evaluation workflow.
3. [`day03_2_student_v1_3.ipynb`](day03_2_student_v1_3.ipynb) implements two-view augmentation, the ResNet-18 encoder and projection head, NT-Xent loss, and experiment code.

## Run notes

- The notebooks target Google Colab and download STL-10 and pretrained ResNet-18 weights.
- Start with the first notebook, then continue in order. Each notebook may require a fresh runtime and its own setup cells.
- Record the runtime type, package versions, seeds, training settings, evaluation protocol, and measured results before comparing runs.
- The saved outputs are from prior notebook sessions; rerun the complete project before presenting them as a reproducible result.

## Scope and limitations

This is a learning and experimentation project. The repository does not yet provide a concise, consolidated experiment report that connects training settings to final evaluation results and limitations. Treat any reported metrics as exploratory until that record is added.
