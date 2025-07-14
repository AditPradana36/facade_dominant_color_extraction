# 🏙️ Dominant Facade Color Extraction from Street-View Imagery (SVI)

This project extracts **dominant facade colors** from urban environments using **semantic segmentation** and **HSV color clustering**. It leverages Google Street View images and pretrained deep learning models to analyze building facades in terms of their **color composition**—a crucial aspect in visual urban studies, architecture, and spatial perception.

---

## 📌 Why This Project?

Understanding the visual character of urban streetscapes—especially facade color tones—can help:

* Inform urban design and facade color regulations.
* Quantify warm vs. cool tone distribution for thermal comfort or aesthetic studies.
* Analyze facade uniformity and diversity across neighborhoods.
* Replicate human-centered street perception using data-driven methods.

---

## 🔍 Methodology Overview

1. **Input**: Street-level panoramic images (e.g., from Google Street View).
2. **Segmentation**: Apply pretrained deep learning model (MIT CSAIL's ADE20K) to isolate **building facades**.
3. **Color Space Conversion**: Convert pixels of segmented facades into HSV color space.
4. **Clustering**: Use **KMeans** to identify 4 dominant HSV colors per image.
5. **Classification**:

   * Classify colors as **Warm** (Hue \~ 0–50, 330–360) or **Cool** (Hue \~ 90–270).
   * Calculate proportion of warm and cool pixels.
6. **Visualization**: Display facade image with color legend and HSV stats.

---

## ✅ Outputs

### 🖼️ Sample Visualization
<img width="1168" height="590" alt="image" src="https://github.com/user-attachments/assets/09a37127-277e-4a48-a65e-f55fea2d7b05" />



This image includes:

* Masked facade segment (black background = non-building).
* Legend of top 4 clustered HSV colors.
* Warm vs Cool hue proportions and HSV cluster stats.

---

### 📊 Hue Composition Table

| Image    | Building Pixels | Warm Pixels | Cool Pixels | Warm % | Cool % |
| -------- | --------------- | ----------- | ----------- | ------ | ------ |
| 4020.jpg | 701,062         | 465,995     | 235,067     | 66.5%  | 33.5%  |
| 4045.jpg | 549,422         | 195,006     | 354,416     | 35.5%  | 64.5%  |
| 4147.jpg | 642,544         | 33,323      | 609,221     | 5.2%   | 94.8%  |
| ...      | ...             | ...         | ...         | ...    | ...    |

---

### 🎨 HSV Cluster Results

Each facade image is clustered into 4 dominant HSV colors, with their weight (proportion):

| Image             | C1 HSV (W)             | C2 HSV (W)             | C3 HSV (W)              | C4 HSV (W)             |
| ----------------- | ---------------------- | ---------------------- | ----------------------- | ---------------------- |
| pointID\_4020.jpg | (45, 0.09, 0.71), 0.36 | (16, 0.27, 0.33), 0.29 | (138, 0.19, 0.37), 0.22 | (65, 0.94, 0.05), 0.13 |
| pointID\_4147.jpg | (90, 0.11, 0.89), 0.39 | (90, 0.29, 0.59), 0.23 | (79, 0.90, 0.10), 0.20  | (76, 0.32, 0.20), 0.19 |
| ...               | ...                    | ...                    | ...                     | ...                    |

---

## 🧑‍💻 How to Run

### 1. Setup Environment

* Python 3.8+
* Google Colab (recommended | this code developed in Google Colab environment)

### 2. Prepare Data

* Place input SVI images in a Google Drive folder
* Format: panoramic `.jpg` images (panoramic form is optional)

### 4. Run the Notebook

* Run `facade_dominant_color_extraction.ipynb` step by step
* Outputs will be saved in determined path that you use:

  * Masked images
  * `building_hue_stats.csv` → warm/cool proportions
  * `dominant_hsv_building_only.csv` → HSV clusters

---

## 🔗 Model Reference

This project adapts segmentation models from:

> **Zhou et al. (2019)** – Semantic Segmentation on ADE20K
> [https://github.com/CSAILVision/semantic-segmentation-pytorch](https://github.com/CSAILVision/semantic-segmentation-pytorch)

---

## 👨‍💼 Author

**Mohammad Raditia Pradana**
Research Assistant — Smart City Universitas Indonesia
> 📧 [radityapradana20@gmail.com](mailto:radityapradana20@gmail.com)
> 🔗 [LinkedIn](https://www.linkedin.com/in/mohammadraditia/)

---

## 📄 License

MIT License — see [`LICENSE`](LICENSE) file for details.
