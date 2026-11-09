# MNIST Boundary Detection and Freeman Chain Code

A Pattern Recognition project that extracts the external contour of a handwritten MNIST digit and encodes its boundary using an 8-connected Freeman Chain Code.

## Workflow
- Load and binarize an MNIST image.
- Detect external contours with OpenCV.
- Select the largest external contour.
- Convert consecutive contour points into 8-direction chain codes.
- Visualize the boundary, sampled directions, and direction distribution.
- Save the resulting chain code to a text file.

## Dataset
MNIST is loaded automatically through `tensorflow.keras.datasets`. No separate dataset folder needs to be uploaded. The first run may require an internet connection.

## Run locally
```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install -r requirements.txt
jupyter notebook
```
Open `MNIST_Boundary_Detection_Chain_Code.ipynb` and run the cells from top to bottom.

## Output
The notebook creates `mnist_chain_code.txt` after successful contour extraction.

## Important notes
- Only external contours are retrieved; internal holes are not included.
- The largest external contour is selected.
- Chain-code output depends on contour start point and traversal direction; normalization is a possible extension.
- This notebook demonstrates boundary representation and does not train a classifier.

## Technologies
Python, OpenCV, NumPy, Matplotlib, TensorFlow/Keras, Jupyter.
