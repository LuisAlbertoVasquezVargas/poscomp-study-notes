<!-- File: computing_technology/computer_graphics/histogram_equalization.md -->

# Histogram Equalization in Image Processing

## 1. Concept

Histogram equalization is a technique in image processing aimed at improving the contrast of an image. It works by **redistributing the intensity levels** so that they span the entire available range more evenly.

## 2. Purpose

* Enhance visual detail.
* Increase the overall contrast of the image.
* Make frequently occurring intensity values less dominant.

## 3. Effects

* A more **uniform histogram** of pixel intensities.
* **Increased variance** in the histogram because pixel values are spread out.
* Objects in the image become **more discriminable** due to better contrast.

## 4. Misconceptions

| Statement                          | Correctness | Explanation                                                               |
| ---------------------------------- | ----------- | ------------------------------------------------------------------------- |
| Minimum detail enhancement         | ❌ Incorrect | Histogram equalization *increases* detail visibility.                     |
| Color domain transformation        | ❌ Incorrect | Primarily operates on intensity or grayscale, not color space conversion. |
| Highest compressibility            | ❌ Incorrect | Spreading values makes data *less* redundant, reducing compressibility.   |
| Lowest discriminability of objects | ❌ Incorrect | Contrast enhancement improves discriminability.                           |
| Maximum variance of histogram      | ✅ Correct   | Spreading intensity levels maximizes histogram variance.                  |

## 5. Key Takeaway

Performing histogram equalization **maximizes the variance of the histogram**, which enhances contrast and reveals image details more clearly.

---
