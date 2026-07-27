# K-Nearest Neighbors (KNN) Classifier in Verilog

A hardware implementation of the **K-Nearest Neighbors (KNN) Classification Algorithm** using **Verilog HDL**. This project demonstrates how the KNN algorithm can be implemented on digital hardware using a Finite State Machine (FSM), Euclidean distance calculation, and majority voting logic.

> Developed as part of Digital IC / FPGA Design training using **Xilinx Vivado**. :contentReference[oaicite:0]{index=0}

---

## 📌 Project Overview

K-Nearest Neighbors (KNN) is one of the simplest supervised machine learning algorithms used for classification. Instead of implementing it in software, this project accelerates the classification process using dedicated digital hardware.

The classifier:
- Accepts an input feature vector.
- Calculates the distance between the input and stored training samples.
- Determines the nearest neighbor(s).
- Predicts the corresponding class.

The design is implemented completely in **Verilog HDL** and verified through simulation in **Vivado**.

---

## 🚀 Features

- Hardware implementation of KNN algorithm
- FSM-based control unit
- Euclidean distance computation
- Sequential processing of training samples
- Class prediction output
- Simulation testbench included
- Synthesizable RTL design

---

## 🛠 Tools Used

- **Language:** Verilog HDL
- **Simulation:** Xilinx Vivado Simulator
- **Design Methodology:** RTL Design
- **Target:** FPGA/Digital Hardware

---

## 📂 Project Structure

```
KNN-Verilog/
│
├── src/
│   ├── knn.v
│   ├── controller.v
│   ├── distance_calculator.v
│   ├── comparator.v
│   └── classifier.v
│
├── tb/
│   └── knn_tb.v
│
├── images/
│   └── waveform.png
│
├── README.md
└── LICENSE
```

> *(Folder names may vary depending on your implementation.)*

---

## ⚙️ Working Principle

1. Reset initializes the classifier.
2. A **Start** signal begins the classification process.
3. Input feature values (`x_in`, `y_in`) are provided.
4. Distances between the input and stored training samples are calculated.
5. The minimum distance is selected.
6. The corresponding class label is assigned to `class_out`.
7. `done` signal goes HIGH when classification is complete.

---

## 📊 Inputs and Outputs

### Inputs

| Signal | Width | Description |
|---------|------:|-------------|
| clk | 1 | System Clock |
| rst | 1 | Reset |
| start | 1 | Starts classification |
| x_in | 16-bit | X coordinate/input feature |
| y_in | 16-bit | Y coordinate/input feature |

### Outputs

| Signal | Width | Description |
|---------|------:|-------------|
| class_out | 1-bit | Predicted class |
| done | 1-bit | Classification completed |
| errors | 32-bit | Error counter (debug) |

---

## 🧠 Architecture

The classifier consists of the following modules:

- FSM Controller
- Distance Calculator
- Comparator
- Minimum Distance Selector
- Class Output Logic

---

## ⏱ Simulation Result

The waveform below shows successful operation of the KNN classifier.

- Reset initialization
- Multiple test vectors
- Correct class prediction
- Completion indicated by the `done` signal

![Simulation Waveform](images/waveform.png)

---

## ✅ Example Test

Example Inputs

| x_in | y_in |
|------:|------:|
| 10 | 10 |
| 12 | 11 |
| 13 | 38 |
| 10 | 10 |

Expected Output

```
Class Prediction → class_out
Done Signal      → HIGH
```

---

## 🎯 Learning Outcomes

Through this project, I gained practical experience in:

- RTL Design
- Verilog HDL
- FSM Design
- Digital Arithmetic
- Hardware Implementation of Machine Learning Algorithms
- FPGA Design Flow
- Functional Simulation using Vivado

---

## 📷 Waveform

> Place your uploaded waveform image inside the `images` folder and rename it as:

```
images/waveform.png
```

The README will automatically display it.

---

## 🔮 Future Improvements

- Support larger datasets
- Configurable K value
- Parallel distance computation
- Manhattan and Minkowski distance metrics
- FPGA implementation and timing optimization
- UART interface for external inputs
- Memory-based training dataset

---

## 👨‍💻 Author

**Muhammad Najid**

Electrical Engineer (Computer Systems Engineering)

Interests:
- Embedded Systems
- FPGA Design
- Digital IC Design
- RTL Development
- Computer Architecture

GitHub: https://github.com/yourusername

---

## ⭐ If you found this project useful, consider giving it a star!
