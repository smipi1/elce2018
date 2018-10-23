# Deep Learning Neural Network Acceleration at the Edge - Andrea Gallo, Linaro

Implications of connecting edge and deep learning

## Why deep learning?

E2E learning for many tasks
Its complex

## From cloud to edge devices

Constraints
* Always online
* Uplink bandwidth / traffic
* Latency vs real-time constraints
* Privacy constraints

Latest application SoC's have neural network capabilities

Ecosystem of companies developing IP

## AI/ML Frameworks

TensorFlow
* 2011 (Then DistBelief)
* Buildable as one of 3 variants:
** TensorFlow for Cloud and datacenters
** TensorFlow Lite for mobile devices
** TensorFlow,js for AI in web browsers
* From TensorFlow to TensorFlow Lite
** Requires converter

Caffe
* For expression, speed and modularity
* Berkley AI
* Vision focus

Caffe2
* Large scale distributed training
* Converter required migrating from Caffe
* Mobile deployment
* New hardware support
* Quantized computing
* Caffe2 and PyTorch join forces

mxnet
* Amazon web services

## Deep learning framework comparison

Estimated cost for cumulative development

## Observation

* Each big cloud vendor has its own deep learning framework
* Each AI framework has own ecosystem
* Each AI framework represents significant investment
* Scaling with hardware accelerators

## Accelerators and software solutions

Google edge TPU
* TensorFlow Lite compute engine
* ML inference @ edge

ARM Mali-G72
* 2nd generation

ARM ML processor
* Best knowledge from GPU and CPU applied for ML
* Adds fixed-function MAC and programmable layer engines
* Self-contained

ARM OD processor
* Real-time object detection @ 60 Hz

ARM NN SDK
* Supports all the above

Snapdragon NPE

Hisilicon
* Huawei silicon division
* Limited information

Large ecosystem of 3rd parties providing NN IP and tools

## Observations

Complete offload vs heterogenous computing
Shared memory vs sub-system memories and DMA
Fixed operators and software fallback
Fraph split vs cost of context switch
Serialized models and converter tools
Forked and accelerated inference engine for each NN IP and framework
* High total cost of ownership
* Delayed rebasing and updates

## Linaro Machine Intelligence Initiative

Common model description format and APIs to the runtime
Common optimized runtime inference engine for ARM
Plug-in framework to support 3rd party NPU, CPU, GPU and DSP
CI loops on reference development boards to measure accuracy. preformance, speed-up and regression testing

Parts:
* ARM donated ARM NN as OSS initiative
* ONNX (Open Neural Network Exchange)
** ONNXIFI (Interface for Framework integration)

Discussion started last March @ Linaro Connect

## TIP: BlackDuck OpenHub web-site to compare open source projects
