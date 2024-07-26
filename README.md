# Knowledge Distillation with MNIST

This repository demonstrates the implementation of knowledge distillation using the MNIST dataset. Knowledge distillation is a technique where a smaller "student" model is trained to mimic the behavior of a larger "teacher" model. This can lead to improved performance and efficiency in the smaller model.

## Overview

- **Teacher Model**: A large neural network trained on the MNIST dataset.
- **Student Model**: A smaller neural network trained using the soft targets produced by the teacher model.
- **Soft Targets**: The output probabilities of the teacher model, adjusted with a temperature parameter.

## Key Components

1. **Data Preparation**: The MNIST dataset is normalized and split into training and test sets.
2. **Teacher Model Training**: A large model is trained on the MNIST training data.
3. **Soft Targets Generation**: The teacher model is used to generate soft targets for the training data.
4. **Student Model Training**: A smaller model is trained using both the original labels and the soft targets.

## Explanation

- **Teacher Model**: The teacher model is a large neural network with multiple dense layers and ReLU activations. It is trained on the MNIST dataset for several epochs.
- **Distillation**: The logits from the teacher model are converted to soft targets using a softmax function with a high temperature. These soft targets contain more information than hard labels and help the student model learn better.
- **Student Model**: The student model is a smaller neural network. It is trained using a custom loss function that combines the traditional cross-entropy loss with the distillation loss derived from the soft targets.

## Performance

The trained student model is evaluated on the MNIST test set to measure its accuracy. Despite being smaller, the student model benefits from the distilled knowledge of the teacher model.

## Acknowledgements

- The MNIST dataset used in this project is provided by Yann LeCun and Corinna Cortes.
- This project leverages TensorFlow for building and training the neural networks.

## References

- Hinton, G., Vinyals, O., & Dean, J. (2015). Distilling the Knowledge in a Neural Network. arXiv preprint arXiv:1503.02531. Retrieved from [arXiv:1503.02531](http://arxiv.org/abs/1503.02531).