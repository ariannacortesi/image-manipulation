# Review notes

## Changes
Added English Markdown section headings and short method explanations. Translated Italian comments and shortened redundant comments and standalone explanatory strings. Preserved all seven code cells, function and variable names, formulas, operations, parameters, saved outputs, and execution counts. Retained the supplied input JPEG and output BMP. Added README, requirements, and gitignore; no modules or new dependencies were introduced. Audio materials and the combined assignment PDF remain in the original TP0 archive.

## Validation
All seven executable cell ASTs match the original after excluding standalone explanatory strings. Both notebooks were executed independently with the supplied JPEG in temporary folders using Matplotlib's noninteractive backend. Six image arrays (input, enhanced, mosaic, grayscale, binary, contours), exported BMP bytes, and printed output matched exactly. Supplied media are copied unchanged. Original saved notebook outputs are retained rather than regenerated. A fresh dependency installation and interactive GUI display were not tested.

## Existing issues intentionally unchanged
- In `imagemCont`, row zero compares against row -1 (the last row), creating wraparound across the image boundary. Column zero is never processed, including for vertical differences. A proposed correction is to check horizontal neighbors only when j > 0 and vertical neighbors only when i > 0, visiting all pixels.
- `imagemMosaico` starts block centers at floor(W/2). A small remainder at the bottom or right can remain unchanged when no center lies within it. Even W produces W+1-pixel blocks stepped by W, causing overlap. Zero or invalid W is not validated. Proposed corrections require deciding whether to process partial blocks and explicitly requiring positive odd integer windows.
- The grayscale coefficients are exactly 0.2978, 0.5870, and 0.1140, summing to 0.9988. The formula slightly reduces a uniform white image to 254 after uint8 conversion. This may be intentional or a transcription issue; verify the assignment before changing coefficients.
- Color enhancement assumes a three-dimensional image with channels on the last axis and values in [0, 255]. It is not generic for grayscale or normalized floating-point inputs. Channel, factor, and threshold are not validated.
- Binary output uses NumPy's integer dtype rather than explicitly uint8; the contour array inherits that dtype. This works in the current pipeline but uses more memory.
- File-size comparisons involve different image content and cannot isolate the effect of JPEG versus BMP compression.

No fixes were applied to these implementation details. The earlier approval to correct the audio notebook was not extended to this separate project.
