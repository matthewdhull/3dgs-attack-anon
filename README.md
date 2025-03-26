# 3D-Gaussian-Splat-Attack

[![BSD-3 license](http://img.shields.io/badge/license-BSD--3-brightgreen.svg)](http://opensource.org/licenses/MIT)

![fig_3-2](https://github.com/user-attachments/assets/6f5b5a2d-8579-42e1-b203-abad5968cf2f)

3D Gaussian Splatting (3DGS) has recently gained traction in safety-sensitive applications such as scene reconstruction, robotic navigation planning, and autonomous vehicle decision-making. However, the increasing reliance on 3DGS in these domains raises security concerns, particularly regarding its vulnerability to adversarial attacks. The 3DGS scene reconstruction algorithm uses gradient optimization with backpropagation to control the color, position, rotation, scaling, and alpha blending of each Gaussian in the scene. 
These optimization methods share intrinsic properties with deep neural network training, enabling known gradient-based DNN exploits to be adapted to 3DGS scenes.  We introduce the CLOAK, the first attack that leverages view-dependent Gaussian appearances—colors and textures that change with viewing angle—to embed adversarial content visible only from specific viewpoints. We further demonstrate DAGGER, a targeted adversarial attack directly perturbing 3D Gaussians without access to underlying training data, deceiving multi-stage object detectors e.g., Faster R-CNN, through established methods such as projected gradient descent. These attacks highlight underexplored vulnerabilities in 3DGS, introducing a new venue for consideration within the adversarial machine learning community for discussion and development of effective defense strategies.

## The 3DGS-Attack pipeline is easy to use!  
`attack.py --model_path /dir/to/model --source_path /dir/to/source/ --combine_splats --combine_splats_paths path/to/target/splat.ply path/to/background/splat.ply --target <class> --epsilon 5.0 --alpha 0.5 --attack_conf_thresh 0.7 --data_device cuda --device 0`

Running this command chooses a "car" 3DGS as the attackable object and a "city" 3DGS as the background, and then optimizes Spherical Harmonic coefficients to make the car appear as a "person"

## Getting Started

Install Detectron2 (Faster R-CNN)

`python -m pip install 'git+https://github.com/facebookresearch/detectron2.git'`

### Model Weights
We use [Robust ImageNet Models](https://huggingface.co/madrylab/robust-imagenet-models). You'll need to choose an appropriate model for your experiment. Currently we use this ResNet-50 [L2-Robust Model](https://huggingface.co/madrylab/robust-imagenet-models/resolve/main/resnet50_l2_eps0.05.ckpt) for object detection with Detectron2. After downloading this model, place it in the `pretrained-models/` directory.  If you want another model, you'll need to create a model config in `configs/model/{model}.yaml`. You may copy the existing configs and use it as a template.

## Documentation

For more detailed information, please refer to the [documentation](docs/DOCUMENTATION.md).
