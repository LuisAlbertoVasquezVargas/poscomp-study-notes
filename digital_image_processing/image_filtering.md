<!-- File: digital_image_processing/image_filtering.md -->

# 🎨 Digital Image Filtering – Key Concepts

Image filtering is used to **modify or enhance** digital images. Filters can be applied either in the **spatial domain** (directly on pixels) or the **frequency domain** (on image’s frequency components).

---

## ✅ Correct Concepts

### 1. Mean Filter (Spatial Domain)
- Performs **smoothing** by replacing each pixel with the average of its neighborhood.
- Reduces noise and blurs the image, softening edges.

### 2. Laplacian Operator (Spatial Domain)
- A second-order derivative filter.
- Used for **sharpening** by emphasizing edges and rapid intensity changes.
- Enhances fine details and contours.

---

## ❌ Common Misconceptions

- **Low-pass frequency filter ≠ sharpening:**  
  Low-pass filters remove high-frequency components (edges, details), causing **smoothing**, not sharpening.

- **Smoothing and sharpening are not exclusive to one domain:**  
  Both can be done in spatial or frequency domains. For example:
  - Smoothing: Mean filter (spatial), Low-pass filter (frequency).
  - Sharpening: Laplacian (spatial), High-pass filter (frequency).

---

## Summary Table

| Filter Type        | Domain        | Effect       |
|--------------------|---------------|--------------|
| Mean Filter        | Spatial       | Smoothing    |
| Low-pass Filter    | Frequency     | Smoothing    |
| Laplacian Operator | Spatial       | Sharpening   |
| High-pass Filter   | Frequency     | Sharpening   |

---

## POSCOMP Tip

- Always link filter types to their **domain** and **effect**.
- Remember:
  - **Smoothing reduces details** and noise.
  - **Sharpening enhances edges** and details.

---
