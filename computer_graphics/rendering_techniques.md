<!-- File: computer_graphics/rendering_techniques.md -->

# 🎨 Rendering Techniques in Computer Graphics

This section covers key rendering techniques and models used in 3D graphics, comparing their principles, realism, and performance characteristics.

---

## 🔦 Ray Tracing

**Ray tracing** is a rendering algorithm that simulates the **physical behavior of light** to produce photorealistic images.

- **Principle**: Casts rays from the camera into the scene to compute visibility, shadows, reflections, and refractions.
- **Realism**: Very high; supports **global illumination** effects.
- **Performance**: Computationally expensive; traditionally not suitable for **real-time applications**.
  - Used in **cinematic rendering**, **3D animation**, and increasingly in modern GPUs with **hardware acceleration**.

---

## 🎯 Z-Buffer (Depth Buffer)

The **Z-buffer** is a visibility determination algorithm used in the **rasterization pipeline**.

- **Principle**: Each pixel stores a **depth value**; when a new fragment is processed, its depth is compared to decide if it should be drawn.
- **Use Case**: Core part of **real-time rendering** (e.g., in video games).
- **Not Ideal for**: High realism or global illumination, as it does not simulate light physics — it's purely geometric.

---

## 💡 Phong Reflection Model

A **local illumination** model used to simulate how surfaces reflect light.

- **Components**:
  - **Ambient**: Constant background light.
  - **Diffuse**: Light scattered in many directions.
  - **Specular**: Sharp reflections like on shiny surfaces.
- **Assumption**: Calculates lighting at a surface point based only on **direct light sources**.
- **Realism**: Limited — does **not** account for **indirect illumination** (e.g., bouncing light).
- **Performance**: Efficient and widely used in **real-time rendering** (e.g., in games).

---

## 📌 Summary Table

| Technique / Model        | Realism       | Performance     | Use Case                    |
|--------------------------|---------------|------------------|-----------------------------|
| **Ray Tracing**          | High (global) | Low (expensive)  | Cinematics, offline render  |
| **Z-Buffer (Rasterization)** | Low (geometry-based) | High (fast)       | Games, real-time engines    |
| **Phong Model**          | Low (local)   | High (fast)      | Games, real-time shading    |

---

## 🧠 Key Concepts to Remember

- **Ray tracing ≠ fast** → known for realism, not efficiency.
- **Z-buffer ≠ realism** → great for visibility, not light simulation.
- **Phong is local** → doesn’t simulate inter-surface light interactions.

---
