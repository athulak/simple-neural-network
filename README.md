# Simple Neural Network

A minimal PyTorch example that trains a linear regression model to estimate bike-delivery time from delivery distance.

The model learns from four distance/time pairs, saves its trained weights, plots the fitted line, and predicts the time required for a seven-mile delivery.

## Requirements

- Python 3.11 or newer
- PyTorch and the dependencies declared in `pyproject.toml`

## Setup

Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install the project and its dependencies:

```bash
python -m pip install --upgrade pip
python -m pip install -e .
```

## Run

From the repository root, run:

```bash
python -m simple_neural_network.train
```

The script trains a single `torch.nn.Linear(1, 1)` layer for 500 epochs using mean squared error loss and stochastic gradient descent. It then:

- prints loss every 50 epochs
- opens a plot comparing the training data with the fitted line
- writes trained weights to `models/model.pth`
- prints the predicted time and a delivery decision for a seven-mile trip
- prints the learned weight and bias

For a non-interactive environment where a plot window cannot be opened, use a non-GUI Matplotlib backend:

```bash
MPLBACKEND=Agg python -m simple_neural_network.train
```

## Project Layout

```text
src/simple_neural_network/train.py        Training and prediction script
src/simple_neural_network/helper_utils.py Plotting helpers
models/                                   Generated model weights
pyproject.toml                            Project metadata and dependencies
```

## Notes

- The training data is intentionally small and hard-coded for demonstration purposes.
- The repository name and package metadata use `nueral`; the Python import package uses the correctly spelled `simple_neural_network`.
- Generated model files under `models/` are ignored by Git.
