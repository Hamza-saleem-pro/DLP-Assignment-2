# Deep Learning for Perception — Assignment 2

This repository contains the completed notebook for Assignment 2. The project uses CIFAR-10 to build and evaluate an image-classification model and investigate data augmentation and regularization.

## Project Contents

- `Assignment2_DLP.ipynb` — Completed notebook.
- `README.md` — Project overview and reproduction instructions.

**Note:** If your notebook has a different filename, update the filename in this README to match it.

## Dataset

CIFAR-10 contains 60,000 colour images of size 32 × 32 across 10 classes: airplane, automobile, bird, cat, deer, dog, frog, horse, ship, and truck.

The notebook uses:

- **Training subset:** 500 images, with 50 images per class.
- **Training/validation split:** 400 training images and 100 validation images.
- **Clean test set:** The original 10,000 CIFAR-10 test images.
- **Shifted test proxy:** A locally generated corruption set based on the clean test images.

The shifted test proxy is generated locally because a separate instructor-provided corrupted test set was not available. Its results should not be described as results on an official or instructor-provided shifted test set.

## Experiments and Evaluation

The notebook includes the implemented model training and evaluation workflow, such as:

- Baseline image classification with an Inception-style module.
- Training and validation learning curves.
- Data augmentation experiments, including geometric and photometric transformations.
- Regularization using techniques such as batch normalization, dropout, and L2 regularization.
- Cutout and mixup/label-smoothing experiments, where included in the notebook.
- Evaluation on clean images and the locally generated shifted test proxy.
- Per-class accuracy, a confusion matrix, and misclassified image examples.
- A grayscale robustness check using a locally generated grayscale proxy.
- Test-time augmentation (TTA) comparison.

Results can vary with software versions, hardware, and randomness. Use the values printed by your own notebook run when reporting final results.

## Requirements

The notebook was developed for a Python environment such as Kaggle Notebooks. It uses:

- TensorFlow / Keras
- NumPy
- Matplotlib
- scikit-learn
- SciPy

The CIFAR-10 dataset is loaded through `tensorflow.keras.datasets.cifar10` and may be downloaded automatically if it is not cached.

## How to Reproduce the Results

### Option 1: Kaggle Notebooks

1. Sign in to [Kaggle](https://www.kaggle.com/).
2. Create a notebook or open your existing Kaggle notebook.
3. Upload or import `Assignment2_DLP.ipynb`.
4. Select a Python environment. Enable GPU acceleration if available; CPU execution may take longer.
5. Run all cells **from top to bottom**.
6. Allow the CIFAR-10 dataset to download if prompted.
7. Review the printed metrics and generated plots.

### Option 2: Run Locally

1. Install Python 3.10 or another version compatible with your TensorFlow installation.
2. Create and activate a virtual environment.
3. Install the required packages:

   ```bash
   python -m pip install --upgrade pip
   python -m pip install tensorflow numpy matplotlib scikit-learn scipy jupyter
   ```

4. Start Jupyter:

   ```bash
   jupyter notebook
   ```

5. Open `Assignment2_DLP.ipynb` and run all cells in order.

For compatibility help, consult the [TensorFlow installation guide](https://www.tensorflow.org/install).

## Reproducibility Notes

- Random seeds are set where implemented, but results may still vary by environment and hardware.
- The training subset is small by design (50 images per class), so interpret results in that context.
- Shifted and grayscale data are locally generated proxies, not official hidden evaluation datasets.
- Changing augmentation or corruption parameters may change the results.
- No pretrained model is required for the small custom-model experiments described here.
- Report metrics from your final notebook run rather than copying values from earlier runs.

## Repository Structure

```text
DLP-Assignment-2/
├── Assignment2_DLP.ipynb
└── README.md
```

To upload through GitHub's website, create a repository, choose **Add file → Upload files**, upload the notebook and this README, then commit the changes.

To upload using Git:

```bash
git init
git add Assignment2_DLP.ipynb README.md
git commit -m "Add completed DLP assignment notebook and README"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```

Replace `YOUR-USERNAME` and `YOUR-REPOSITORY` with your GitHub username and repository name.

## References

- [CIFAR-10 Dataset](https://www.cs.toronto.edu/~kriz/cifar.html)
- [TensorFlow CIFAR-10 Loader](https://www.tensorflow.org/api_docs/python/tf/keras/datasets/cifar10)
- [GitHub README Documentation](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes)

