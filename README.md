# DL_GAN_202502

## Contents
- [References](#references)
- [File Structure](#file-structure)
- [Usage](#usage)
- [License](#license)

## References
- [Ian J. Goodfellow et al., "Generative Adversarial Networks," 2014. ](https://arxiv.org/abs/1406.2661)
- [Alec Radford et al., "Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks," 2015.](https://arxiv.org/abs/1511.06434)

## File Structure
```
├── GAN_mnist.ipynb              # Jupyter notebook for training GAN on MNIST
├── LICENSE                      # MIT License file
├── README.md                    # Project documentation
├── load_trained_model.ipynb      # Notebook for loading trained models
├── models_archive
│   └── celeba                     # Pretrained GAN models on CelebA dataset
├── output_images                  # Generated images from GAN
├── requirements.txt               # Required packages for the project
├── setup_virtual_environment.bash # Script to set up the virtual environment
└── training_dcgan_faces.ipynb      # Jupyter notebook for extensive GAN training
```

## Usage
### 1. Clone this repository
```zsh {iscopy=true}
git clone https://github.com/ichiro0709/DL_GAN_202502.git
cd DL_GAN_202502
```
### 2. Set up the virtual environment(Python venv)
This project was executed using Python 3.11.3. It may not work correctly with Python 3.13.

```bash
./setup_virtual_environment.bash
```
Note: It is not strictly required to follow this, but when loading a pre-trained model, ensure that the PyTorch version matches the one used during training. (In my environment, I used PyTorch==2.6.0).



### 3. Run th code
- If you want a **quick test**, run `GAN_mnist.ipynb`.
- If you have **GPU resources available**, run `training_dcgan_faces.ipynb` for more extensive training.
- If you have a **pre-trained model** (generated using `training_dcgan_faces.ipynb`), run `load_trained_model.ipynb` to generate images.

**Note:** When running `training_dcgan_faces.ipynb`, you need to download and set up the CelebA dataset. Download `img_align_celeba.zip` from the provided link or Google Drive, extract it into a `celeba` directory, and set the `dataroot` input in the notebook to point to this directory. The directory structure should be:

```
/path/to/celeba
    ├── img_align_celeba
        ├── 188242.jpg
        ├── 173822.jpg
        ├── 284702.jpg
        ├── 537394.jpg
        └── ...
```

This setup is required because the `ImageFolder` dataset class expects subdirectories within the dataset root folder.



# DCGAN with PyTorch

This project is based on the official PyTorch tutorial:
- [PyTorch DCGAN Tutorial](https://colab.research.google.com/github/pytorch/tutorials/blob/gh-pages/_downloads/5f81194dd43910d586578638f83205a3/dcgan_faces_tutorial.ipynb)

## License
This project is licensed under the MIT License.

## Credits
The base implementation is adapted from the official PyTorch tutorial.
