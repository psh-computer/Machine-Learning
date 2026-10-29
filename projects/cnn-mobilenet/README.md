# CNN and Depthwise Separable Convolution

This project implements a standard convolution block and a depthwise-separable block inspired by MobileNet.

## Files

- [`CNNvsMobileNet.ipynb`](CNNvsMobileNet.ipynb): defines both blocks and checks their output shapes on a synthetic input.

## Current status

The notebook does not yet measure parameter counts, inference time, or classification accuracy. The repository therefore demonstrates the block implementations, not a completed efficiency comparison.

## Next experiment

Compare the blocks with the same input shape and hardware. Report parameter counts, warmed-up repeated inference timings with variability, and accuracy on a defined dataset and split. Record the device, runtime, and measurement procedure.
