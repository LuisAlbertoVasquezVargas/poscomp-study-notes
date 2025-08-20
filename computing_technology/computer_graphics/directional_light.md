<!-- File: computing_technology/computer_graphics/directional_light.md -->

# Lighting in 3D Graphics – Directional Light

## 1. Light Source Types Overview

In 3D rendering and graphics, light sources can be classified into several types based on how they emit light:

* **Point Light:** Emits light equally in all directions from a single point in space.
* **Spot Light:** Emits light in a cone-shaped area, useful for focused illumination.
* **Directional Light:** Simulates light from a source that is infinitely far away.

## 2. Directional Light

* **Definition:** A light source located at an effectively infinite distance, generating parallel light rays.
* **Purpose:** Simulates sunlight or other distant light sources.
* **Characteristics:**

  * All rays have the same direction.
  * No attenuation based on distance.
  * Useful for outdoor scenes or any scenario requiring uniform directional illumination.

## 3. Comparison with Other Light Types

| Light Type        | Source Location   | Ray Behavior                   | Typical Use Case            |
| ----------------- | ----------------- | ------------------------------ | --------------------------- |
| Point Light       | Specific point    | Radiates in all directions     | Lamps, bulbs, candles       |
| Spot Light        | Specific point    | Radiates within a cone         | Flashlights, stage lighting |
| Directional Light | Infinite distance | Parallel rays in one direction | Sunlight, moonlight         |

---
