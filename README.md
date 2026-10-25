# Image Manipulation

University Python exercises covering basic RGB image processing with NumPy and Matplotlib. The notebook preserves the original algorithms and execution sequence.

## Objectives
- Load and display an RGB image.
- Enhance one color channel with clipping.
- Create a mosaic using central pixel colors.
- Convert RGB values to grayscale using the original weighted sum.
- Apply binary thresholding and detect neighboring-pixel differences.
- Export contours to BMP and inspect file sizes.

## Project structure
- `mainImage.ipynb`: documented exercise sequence with original saved outputs.
- `polarbear.jpg`: original input image.
- `polarbear_contour.bmp`: supplied contour output; overwritten when the last cell runs.
- `REVIEW_NOTES.md`: validation and existing technical limitations.
- `requirements.txt`: directly used project libraries.

## How to run
Use Python 3 and run from this folder:

```bash
python -m pip install -r requirements.txt
python -m pip install notebook
python -m notebook mainImage.ipynb
```

Run all cells in order. Jupyter is installed separately as the notebook execution tool. No additional image-processing packages are needed directly by the code.

## Outputs
The notebook displays the input, blue-channel enhancement, mosaic, grayscale image, binary mask, and contour image. It writes `polarbear_contour.bmp` and prints JPEG and BMP file sizes. These files contain different image content, so their size difference is not a controlled comparison of compression formats.
