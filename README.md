
# 🖼️ Image Enhancement using OpenCV

A beginner-friendly yet powerful computer vision project that enhances images using **Histogram Equalization** and **Morphological Operations**. This project is ideal for understanding basic image preprocessing techniques that are widely used in OCR, medical imaging, and document enhancement pipelines.

> 💡 Real-world use case | 📷 Computer Vision | 🔧 OpenCV & NumPy

---

## 📌 Project Overview

This project enhances an input image using:

- **Grayscale Conversion**
- **Histogram Equalization** (for contrast enhancement)
- **Otsu’s Thresholding** (for binarization)
- **Morphological Opening** (to remove noise)

Each transformation is visualized and saved for further use.

---

## 🧪 Technologies Used

- Python 3.x
- OpenCV
- NumPy
- Matplotlib

---

## 🖼️ Input Image

Replace `Maggie.jpg` with any image you want to enhance:

```

📂 your-project-folder/
├── Maggie.jpg
├── script.py
└── \[Generated Output Images]

````

---

## 🛠️ Processing Steps

### ✅ 1. Grayscale Conversion

Converts the original image into grayscale to reduce dimensionality while retaining essential structure.

```python
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
````

---

### ✅ 2. Histogram Equalization

Improves image contrast by redistributing the intensity values.

```python
HistEq = cv2.equalizeHist(gray)
```

---

### ✅ 3. Otsu’s Thresholding + Morphological Opening

Performs automatic thresholding followed by morphological operations to reduce noise and enhance features.

```python
binr = cv2.threshold(gray, 0, 255, cv2.THRESH_BINARY+cv2.THRESH_OTSU)[1]
kernel = np.ones((3, 3), np.uint8)
opening = cv2.morphologyEx(binr, cv2.MORPH_OPEN, kernel, iterations=1)
```

---

## 📸 Output Visualization

| Original                 | Grayscale            | Histogram Equalized     | Morphologically Enhanced |
| ------------------------ | -------------------- | ----------------------- | ------------------------ |
| ![](assets/original.jpg) | ![](assets/gray.jpg) | ![](assets/hist_eq.jpg) | ![](assets/morph.jpg)    |

> 📂 Outputs saved as:

* `GrayImg.jpg`
* `HistogramEqualization.jpg`
* `MorphologicalOperation.jpg`

---

## 🎯 Applications

* OCR Preprocessing
* Medical Imaging (X-rays, CT scans)
* Satellite Image Enhancement
* Document Noise Removal

---

## 🧰 Run the Project

Clone the repository and run the script:

```bash
git clone https://github.com/your-username/image-enhancement-opencv.git
cd image-enhancement-opencv
pip install -r requirements.txt
python script.py
```

Make sure to replace `Maggie.jpg` with your own input image.

---

## 🌟 Star this repo

If you found this project helpful or insightful, please consider giving it a ⭐ on GitHub — it motivates continued learning and open-source contributions.

---

## 🧑‍💻 Author

**Varun Haridas**
📧 [varun.haridas321@gmail.com](mailto:varun.haridas321@gmail.com)
🔗 [LinkedIn](https://linkedin.com/in/your-profile) • [GitHub](https://github.com/your-username)

---

## 📝 License

This project is licensed under the MIT License.

```

---

### Optional Enhancements You Can Add:
- Save a combined output image of all 4 subplots (`plt.savefig()`).
- Create a GUI using `Tkinter` or a web app using `Gradio/Streamlit`.
- Add timing benchmarks or FPS for real-time enhancement.
