# Learning Statistical Learning — Notebooks from Three Courses

Notebooks worked through while learning machine learning and deep learning, kept
together so the progression from "run the textbook code" to "implement the layer
yourself" stays visible.

They come from three different sources, and each is credited below. **This
repository is a study log, not original work**: the notebooks are the upstream
material as executed, annotated and occasionally modified. All of them open in
Google Colab from the badge at the top.

## 1. Classical machine learning — Géron

From [**Hands-On Machine Learning with Scikit-Learn, Keras & TensorFlow**](https://github.com/ageron/handson-ml3)
by Aurélien Géron (3rd edition).

| Notebook | Content |
| --- | --- |
| `01_the_machine_learning_landscape.ipynb` | Chapter 1: supervised vs. unsupervised, instance- vs. model-based learning, the main pitfalls (overfitting, non-representative data), and the life-satisfaction/GDP linear model built from the OECD and IMF data |
| `02_end_to_end_machine_learning_project.ipynb` | Chapter 2: the full California-housing project end to end — stratified train/test splitting, exploratory analysis, preprocessing pipelines and custom transformers, model selection, cross-validation, grid search, and evaluation on the test set. The long one, and the one worth returning to |

## 2. Deep learning with PyTorch — De Nobili

A PyTorch course by **Cristiano De Nobili**, taken in order. This is the
sequence where the mathematics gets implemented rather than called.

| Notebook | Content |
| --- | --- |
| `1_deep_learning_theory_with_pytorch.ipynb` | Tensors, autograd, and the theory of feed-forward networks in PyTorch terms |
| `2_mlp_from_scratch.ipynb` | **A multi-layer perceptron written from scratch** — forward pass, loss, backpropagation and the update step, without `nn.Module` doing the work |
| `3_mlp_mnist_training.ipynb` | The same MLP trained on MNIST, with hyperparameter search via **Optuna** and `torchsummary` for the architecture |
| `4_the_convolutional_layer.ipynb` | The convolutional layer: kernels, stride, padding and receptive fields, worked on real images with `PIL` and OpenCV |
| `5_denoising_vae.ipynb` | A **denoising variational autoencoder** — the latent space, the reparameterisation trick, and the KL term |
| `6_dcgan.ipynb` | A **DCGAN**: generator and discriminator trained against each other, with the usual instabilities on display |

## 3. Finance application

| Notebook | Content |
| --- | --- |
| `Finance_101_1_Stocks_Data_Analysis_and_Visualization.ipynb` | Stock data analysis and visualisation with `pandas`, `plotly` and `seaborn`: daily returns, normalisation, correlation between tickers, and interactive charts |

Its dataset is committed as **`stock.csv`** — daily closes from January 2012 for
AAPL, BA, T, MGM, AMZN, IBM, TSLA, GOOG and the S&P 500 index.

## Running the notebooks

Click the Colab badge at the top of a notebook — the recommended route for the
deep-learning ones, which want a GPU — or run locally:

```bash
pip install numpy pandas matplotlib scikit-learn
pip install torch torchvision torchsummary optuna    # for notebooks 1-6
pip install plotly seaborn opencv-python             # for the finance notebook
jupyter lab
```

The Géron notebooks download their datasets on first run. Only the finance
notebook reads a committed file (`stock.csv`); it was written for Colab, so its
data-loading cell may need the path adjusting when run locally.

## Related repository

- [`learning_econophysics`](https://github.com/alessiomartini/learning_econophysics)
  — the same approach applied to stochastic processes in finance: fractional
  Brownian motion, Ornstein–Uhlenbeck, and multifractality.
