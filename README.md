# Learning Adaptive Hierarchical Cuboid Abstractions of 3D Shape Collections

<img src="teaser.png" alt="teaser" width=800px; height=373px;/>

## Introduction

This work is based on our SIGA'19 paper. We proposed an unsupervised learning method for 3D shape abstractions. You can check our [project webpage](https://isunchy.github.io/projects/cuboid_abstraction.html) for a quick overview.

Abstracting man-made 3D objects as assemblies of primitives, i.e., shape abstraction, is an important task in 3D shape understanding and analysis. In this paper, we propose an unsupervised learning method for automatically constructing compact and expressive shape abstractions of 3D objects in a class. The key idea of our approach is an adaptive hierarchical cuboid representation that abstracts a 3D shape with a set of parametric cuboids adaptively selected from a hierarchical and multi-level cuboid representation shared by all objects in the class. The adaptive hierarchical cuboid abstraction offers a compact representation for modeling the variant shape structures and their coherence at different abstraction levels. Based on this representation, we design a convolutional neural network (CNN) for predicting the parameters of each cuboid in the hierarchical cuboid representation and the adaptive selection mask of cuboids for each input 3D shape. For training the CNN from an unlabeled 3D shape collection, we propose a set of novel loss functions to maximize the approximation quality and compactness of the adaptive hierarchical cuboid abstraction and present a progressive training scheme to refine the cuboid parameters and the cuboid selection mask effectively.

In this repository, we release the code and data for training the abstraction networks on 3D objects in a class.

## Citation

If you use our code for research, please cite our paper:
```
@article{sun2019abstraction,
  title     = {Learning Adaptive Hierarchical Cuboid Abstractions of 3D Shape Collections},
  author    = {Sun, Chunyu and Zou, Qianfang and Tong, Xin and Liu, Yang},
  journal   = {ACM Transactions on Graphics (SIGGRAPH Asia)},
  volume    = {38},
  number    = {6},
  year      = {2019},
  publisher = {ACM}
}
```

## Setup

Pre-prequisites

        Python == 3.6
        TensorFlow == 1.12
        numpy-quaternion

Compile customized TensorFlow operators

        $ cd cext
        $ mkdir build
        $ cd build
        $ cmake ..
        $ make

## Experiments


### Data Preparation

Now we provide the Google drive link for downloading the training datasets:

>[Training data](https://drive.google.com/drive/folders/1Uh_-CrOyUVpB5mWkSOY-L-b2kpa9LuTC?usp=sharing)

### Training

To start the training, run

        $ python training_script.py --category class_name

### Test

To test a trained model, run

        $ python iterative_training.py --test_data test_tfrecords --test_iter number_of_shapes --ckpt /path/to/snapshots --cache_folder /path/to/save/test_results --test

Now we provide the trained weights and the final results used in our paper:

>[Weights](https://drive.google.com/drive/folders/1ipixLDU4LejE57R8dnLJFTvGvnkilfv_?usp=sharing)

>[Results](https://drive.google.com/drive/folders/1e_qdJeFtNoPy8jtBKtpMoln-Cfrn8Jya?usp=sharing)
 

## License

MIT Licence

## Contact

Please contact us (Chunyu Sun sunchyqd@gmail.com, Yang Liu yangliu@microsoft.com) if you have any problem about our implementation.
