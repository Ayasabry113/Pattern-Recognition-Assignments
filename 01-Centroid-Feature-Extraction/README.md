# MNIST Centroid-Based Feature Extraction

A Pattern Recognition assignment implementing block-based centroid feature extraction on handwritten MNIST digits.

## Method
1. Load the MNIST dataset using TensorFlow/Keras.
2. Convert grayscale images into binary images using a configurable threshold.
3. Divide each image into a configurable grid.
4. Calculate the row and column centroid of foreground pixels in every block.
5. Concatenate the centroid coordinates into a feature vector.
6. Visualize the grid and centroids, then export training and test features to CSV.

## Feature representation
For a grid with `R` rows and `C` columns, each image is represented by `2 × R × C` features. Empty blocks return `(0, 0)`, matching the assignment's original convention.

## Dataset
MNIST is loaded automatically through `tensorflow.keras.datasets`. No manual dataset download or upload is required. The first run may need an internet connection.

## Run
```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install -r requirements.txt
jupyter notebook
```
Open `MNIST_Centroid_Feature_Extraction.ipynb` and run all cells.

## Output files
The notebook generates:
- `mnist_centroid_features_train.csv`
- `mnist_centroid_features_test.csv`

These files are generated when the notebook runs; they do not need to be committed to GitHub unless you want to publish sample outputs.

## Scope and limitation
This notebook performs feature extraction, not classification. It does not train or evaluate a classifier. Centroid features capture coarse spatial distribution but do not preserve all image-shape information.

## Technologies
Python, NumPy, Pandas, Matplotlib, TensorFlow/Keras, Jupyter.
