<!-- File: digital_image_processing/sampling_quantization.md -->

# 🖼️ Sampling and Quantization in Digital Image Processing

When an analog image is converted into a digital image through digitization, two key steps are involved:

---

## 1. Sampling

- **Definition:** The process of discretizing the spatial coordinates of the image.
- **What it does:** Converts the continuous spatial domain (the real-world image) into a discrete grid of pixels.
- **Result:** A matrix of pixel locations representing the image structure.

---

## 2. Quantization

- **Definition:** The process of discretizing the amplitude values of the pixels.
- **What it does:** Maps continuous pixel brightness or color intensity values into a finite set of discrete levels.
- **Result:** Each pixel is assigned a finite numerical value, enabling digital representation.

---

## Summary

| Step       | Description                         | Domain         |
|------------|-----------------------------------|----------------|
| Sampling   | Discretizes spatial coordinates   | Spatial domain |
| Quantization | Discretizes pixel amplitude values | Amplitude domain |

---

## POSCOMP Tip

- Remember:  
  - **Sampling** = “Where” (pixel locations)  
  - **Quantization** = “What” (pixel intensity/color levels)

---
