# 🏗️ Sketch-to-Building AI Generator

Turn your architectural sketches into **photo-realistic building renders** using **ControlNet + Stable Diffusion**, with advanced **prompt engineering** — built for the **WHERENESS AI Take-Home Challenge**.

---

## 🚀 Live Demo

🔗 [Click here to try the hosted app](https://your-gradio-link-here.com)  
⚠️ You can upload your own sketch and press **Generate** — no setup required.

---

## 🧠 Project Overview

This project transforms **hand-drawn architectural sketches** into **realistic building images** using:

- `ControlNet (Canny)` to enforce structural precision
- `Realistic Vision V6` as the base model for photorealism
- Carefully crafted fixed prompt for consistency
- Web UI powered by Gradio

---

## 📥 Input Sketch (Example)

<img src="examples\whereness assignment sketch.png" width="400"/>

---

## 🖼️ Output Images

| Generated Image 1                                                        |
| ------------------------------------------------------------------------ |
| <img src="examples\whereness assignment sketch-output.jpg" width="400"/> |

---

## 🔧 Core Strategy: Prompt Engineering + Pretrained Models

Rather than fine-tuning, this solution **strategically leverages pre-trained models** and **prompt design** to generate outputs that:

- Match the **number of windows**
- Respect the **structure and layout**
- Include realistic **construction materials**

---

## 🧱 Model Architecture

| Component  | Description                                                    |
| ---------- | -------------------------------------------------------------- |
| ControlNet | `lllyasviel/control_v11p_sd15_canny` – for sketch conditioning |
| Base Model | `SG161222/Realistic_Vision_V6.0_B1_noVAE` – photo-realism      |
| Scheduler  | `UniPCMultistepScheduler`                                      |
| Frameworks | PyTorch, Diffusers, OpenCV, PIL, Gradio                        |

---

## 🧾 Prompt Engineering Strategy

### ✅ Fixed Positive Prompt (internal):

"clear sky, sunny day, architecture, FullHD, residential, photo realistic, hyperrealistic, super detailed, intricate, shadows, high dynamic range, reflecting window, raytracing"

---

## 📐 Input Processing Flow

1. Sketch is resized and converted to grayscale.
2. Canny edge detection generates an edge map.
3. The map is passed to ControlNet to guide image generation.
4. The model combines this map with fixed and additional prompts to output photo-realistic architectural images.

---

## 💻 Web Interface (Gradio)

- Built with **Gradio Blocks** for modular and interactive design.
- Upload your hand-drawn sketch.
- Click `Generate` to view the AI-generated photorealistic building image.
- Customize optional advanced settings: resolution, Canny thresholds, steps, seed, etc.

### Screenshot:

![Gradio UI](examples/ui_screenshot.png)

---

## 🎨 Example Results

| Sketch Input             | AI Generated Output       |
| ------------------------ | ------------------------- |
| ![](examples/input1.jpg) | ![](examples/output1.jpg) |
| ![](examples/input2.jpg) | ![](examples/output2.jpg) |

> All images maintain **window count, structure fidelity**, and showcase **realistic lighting/materials**.

---
