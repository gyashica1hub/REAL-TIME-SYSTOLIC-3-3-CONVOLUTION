# Real-Time Systolic 3×3 Convolution for Video Sharpening

This project demonstrates a **real-time video sharpening system** using a **3×3 systolic-style convolution pipeline** implemented in Python with **OpenCV** and **NumPy**. The design mimics the behavior of **systolic arrays** commonly used in hardware accelerators (DSPs, FPGAs, ASICs) while remaining fully software-based.

---

## 📌 Key Features

* 🎥 **Live webcam processing** using OpenCV
* ⚙️ **Systolic-style 3×3 convolution** (pipeline-based row shifting)
* ⚡ **Vectorized computation** for high FPS
* ✨ **Accurate image sharpening** using a standard Laplacian-based kernel
* 📊 **Real-time FPS display**

---

## 🧠 Concept Overview

### What is Systolic Convolution?

A systolic array processes data in a **rhythmic, pipelined manner**, where intermediate results flow through processing elements. In this project:

* Image rows are shifted through buffers (`w0`, `w1`, `w2`)
* Each buffer represents a pipeline stage
* Convolution is performed once all stages are filled

This approach is inspired by **hardware-efficient convolution designs** used in CNN accelerators.

---

## 🧮 Sharpening Kernel Used

The following 3×3 kernel enhances edges while preserving image clarity:

```
[ 0  -1   0 ]
[ -1  5  -1 ]
[ 0  -1   0 ]
```

This kernel:

* Boosts the center pixel
* Subtracts neighboring pixels
* Produces a sharp and clean output

---

## 🗂️ Project Structure

```
.
├── main.py        # Real-time video processing with systolic convolution
├── README.md      # Project documentation
```

---

## ▶️ How It Works (Flow)

1. Capture video frames from the webcam
2. Convert frames to grayscale
3. Apply padding using border reflection
4. Load image rows into systolic buffers
5. Perform vectorized 3×3 convolution
6. Normalize output to display range (0–255)
7. Display original and processed frames with FPS

---

## 🛠️ Requirements

Make sure you have the following installed:

* Python 3.8+
* OpenCV
* NumPy

Install dependencies using:

```
pip install opencv-python numpy
```

---

## 🚀 How to Run

1. Connect a webcam
2. Run the script:

```
python main.py
```

3. Press **`q`** to exit the application

---

## 📈 Performance Notes

* Uses **NumPy vectorization** instead of nested loops
* Achieves real-time performance on CPU
* FPS depends on camera resolution and system specs

---

## 🔬 Applications

* Real-time image enhancement
* Hardware-inspired vision algorithms
* Edge detection and sharpening
* Computer vision preprocessing pipelines
* Academic demonstrations of systolic arrays

---

## 📚 Future Improvements

* Extend to **5×5 or NxN kernels**
* CUDA / GPU acceleration
* FPGA or Verilog implementation
* Integration with CNN layers
* Multi-channel (RGB) convolution

---

## 👩‍💻 Author

Developed for educational and experimental purposes, combining **computer vision** with **hardware-inspired algorithm design**.

---

⭐ If you found this useful, consider extending it into a CNN or hardware accelerator project!
