# 🔍 License Plate Detection & Character Recognition

This project is an end-to-end system for automatic license plate detection and character recognition. It combines **transfer learning**, **custom CNN architectures**, **NdLinear layers**, and advanced **bounding box loss functions (CIoU)** to achieve high performance on multi-country datasets.

---

## ✨ Powered by NdLinear (from Ensemble AI)

### 🔹 NdLinear: A Next-Gen Replacement for `nn.Linear`
You have found **NdLinear by [Ensemble AI](https://ensembleai.org)** — a modern reimagining of PyTorch’s linear layers. We use it at the heart of this project to improve both **bounding box regression** and **character classification**.

**Why NdLinear?**
- 🧠 **Structure Preservation**: Retains the multi-dimensional format of tensors, ideal for image-like and spatiotemporal data.
- ⚡ **Parameter Efficiency**: Reduces the number of learnable parameters without compromising on performance.
- 🔄 **Seamless Drop-in**: Works as a drop-in replacement for `nn.Linear` in existing architectures.
- 🚀 **Minimal Overhead**: Matches the computational cost of traditional linear layers while expanding representational power.

In our experiments, models using **NdLinear converged faster and achieved better generalization**—especially noticeable in:
- Higher **validation IoU** for bounding box models.
- Higher **accuracy** and lower **loss** in character recognition.

---

## 🚀 Project Highlights

### ✅ 1. ResNet101 + NdLinear for Bounding Box Regression
- Combines pretrained **ResNet101** features with **NdLinear** heads.
- Outperforms traditional FC layers in IoU and mAP@0.5.
- Employs **CIoU loss** for geometric-aware regression.

### 🧠 2. Custom CNN for Character Recognition
- Two variants: `CharCNNLinear` and `CharCNNNdLinear`.
- The NdLinear version delivers better accuracy with fewer parameters.

### 🫲 3. CIoU Loss for Bounding Box Training
- Combines overlap, center distance, and aspect ratio penalties.
- Used in a hybrid loss: `α * SmoothL1 + (1 - α) * CIoU`.

### 🛍️ 4. Early Stopping for Efficient Training
- Stops training when validation IoU plateaus.
- Saves best model based on IoU and logs results to CSV.

### 🧹 5. Character Segmentation with OpenCV
- Rule-based system for segmenting license plate characters.
- Works across different countries and fonts.

---

## 📊 Visualizations

- 📈 Training history comparison: `loss`, `accuracy`, `IoU`, and `epoch time`.
- 🅰️ Character predictions with image overlays.
- 🔵 Bounding boxes with confidence and label.

---

## 🛠️ Tech Stack

- **PyTorch**
- **NdLinear by Ensemble AI**
- **OpenCV**
- **Matplotlib + Seaborn**
- **Pandas**

---

## 📌 Noteworthy Features

- 🔹 **NdLinear**: Innovative architecture for deep learning over structured tensors.
- 🧠 **Transfer Learning**: Fast convergence using pretrained backbones.
- 🌟 **CIoU Loss**: Geometrically aware localization.
- 🔄 **Rule-based Segmentation**: Character-wise cropping.
- 🛑 **Early Stopping**: Training efficiency + generalization.
- 🌍 **Multi-country Support**: Easily extendable dataset format.

---

## 🧐 Future Work

- [ ] DETR-based bounding box model
- [ ] Multilingual plate support
- [ ] Real-time inference on edge devices (Jetson, Coral)
- [ ] Semi-supervised character segmentation

---

## 👥 Credits

Special thanks to **Ensemble AI** for building and sharing **NdLinear** — a foundational component of this project.

---

## 📜 License

MIT License - see the [LICENSE](LICENSE) file for details.

