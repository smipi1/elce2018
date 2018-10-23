# Deep Learning in OpenCV - Wu Zhiwen, Intel

## What is OpenCV

OS Cumpute Vision library
2500+ algorithms
C/C++/Python
20K+ forks
OpenCV 4.0
* C++ 11
* Binary incompatible
* Improved perf
* Reduced memory consumption

## Key concepts of DNN

Node / Neuron / Perceptron
* Weighted inputs
* Net input function
* Activation function

Layers
* Input
* Hidden
* Output

Training
1. Initialize weights
1. Set input data and compute network output
1. Compare out and ground truth calc err
1. Modify weights and repeat from 2.

Inference

Use cases
* Face recognition
* Pixel segmentation
* Object recognition

## OpenCV DNN module

Inference only
Compatible with many Deep Learning frameworks
Why something new?
* Lightness
* Convenience
* Universality
** Unified IF to manipulate net models from different frameworks

## DNN Module arch

Layers:
* Language bindings / Accuracy test, Perf test, Seamples
* Top level C++ API
* Implementatoin level
* Acceleration layer: SSE, AVX, parallel_for (CPU) / OpenCL (GPU) / Halide (CPU,GPU) / Intel IE (specialized HW)

## Network optimizations

Not tied to any speficif Deep Learning frameworks

## Layer fusion

Can merge layers together to reduce network complexity / computation workload

## Memory reuse

Reuse input memory (in-place computation)
Reuse memory allocated at lower layer

## OpenCL acceleration

Built-in implementation
No ext dependency, except for OpenCL runtime
FP32 and FP16
Highly optimized convolution kernels
Use auto-tuning to get best from you hardware
Neo driver gives better performance on Intel GPU

## Vulkan backend

Next gen from OpenGL community
Extend GPU use



