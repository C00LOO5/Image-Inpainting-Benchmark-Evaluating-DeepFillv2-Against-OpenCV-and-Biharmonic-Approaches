# Image Inpainting Benchmark: Evaluating DeepFillv2 Against OpenCV and Biharmonic Approaches

A comparative study of image inpainting algorithms using traditional OpenCV methods, biharmonic models, and advanced deep learning with DeepFillv2. This interactive tool allows users to upload or capture images, mask regions to be inpainted, and evaluate the results across multiple algorithms.

![demo](https://user-images.githubusercontent.com/demo-placeholder.png)

---

## Features

- **Interactive Web App** using Streamlit + drawable canvas  
- **Deep Learning**-based inpainting using **DeepFillv2**  
- Traditional OpenCV methods: `INPAINT_TELEA`, `INPAINT_NS`  
- Custom **Biharmonic Inpainting** using Laplacian methods  
- Quality metrics: **PSNR**, **MSE**, and **SSIM**  
- Dataset selector: `places2`, `celebahq`  

---

## 🛠️ Tech Stack

| Component         | Library/Tool                    |
|------------------|---------------------------------|
| Web UI           | `Streamlit`, `streamlit-drawable-canvas` |
| Inpainting       | `OpenCV`, `Scikit-Image`, `DeepFillv2`, `Torch` |
| Metrics          | `cv2.PSNR`, `SSIM`, `MSE` |
| Visualization    | `Matplotlib`, `PIL` |
| Dependencies     | See [`requirements.txt`](./requirements.txt) |

---

## How to Run

### 1. Clone the Repository

```bash
gh repo clone C00LOO5/Image-Inpainting-Benchmark-Evaluating-DeepFillv2-Against-OpenCV-and-Biharmonic-Approaches
```

### 2. Set Up Environment

```bash
pip install -r requirements.txt
```

### 3. Download Pretrained Models

Place the following pretrained `.pth` files under a folder named `pretrained/`:
- `states_tf_places2.pth`
- `states_tf_celebahq.pth`

> These can be obtained from the [DeepFillv2 GitHub repo](https://github.com/JiahuiYu/generative_inpainting).

### 4. Run the Streamlit App

```bash
streamlit run main_page.py
```

---

## Evaluation Metrics Explained

From `Paramerters for Inpainting Evaluation.txt`:

| Metric | Meaning |
|--------|---------|
| **PSNR** | Higher is better – less noise compared to original |
| **MSE** | Lower is better – fewer pixel-wise errors |
| **SSIM** | Closer to 1 is better – structural similarity |

---

## Example Outputs

| Input | Mask | TELEA | NS | DeepFillv2 |
|-------|------|-------|----|------------|
| ![](example1.png) | ![](mask1.png) | ![](telea.png) | ![](ns.png) | ![](deepfillv2.png) |

---

## File Structure

```bash
.
├── deepfillv2.py           # DeepFillv2 model wrapper
├── main.py                 # Traditional inpainting functions
├── main_page.py            # Streamlit app
├── requirements.txt
├── pretrained/             # Folder for DeepFillv2 .pth files
└── Paramerters for Inpainting Evaluation.txt
```

---

## Result Summary (Sample)

| Algorithm              | PSNR  | MSE   | SSIM |
|------------------------|-------|-------|------|
| TELEA (OpenCV)         | 25.34 | 312.1 | 0.89 |
| NS (OpenCV)            | 23.12 | 528.4 | 0.83 |
| DeepFillv2: Places2    | 30.12 | 212.3 | 0.92 |
| DeepFillv2: CelebA-HQ  | 31.76 | 189.6 | 0.95 |

---

## License

This project is for academic and research use only. DeepFillv2 components are under the [MIT License](https://github.com/JiahuiYu/generative_inpainting/blob/master/LICENSE).

---

## Acknowledgements

- [DeepFillv2 by Jiahui Yu](https://github.com/JiahuiYu/generative_inpainting)
- OpenCV, SciPy, and Scikit-Image contributors
- Streamlit Community
