# Fire Detection on Edge (C++ / MCU)

An AI-powered fire detection system optimized for microcontrollers. This project uses a quantized Convolutional Neural Network (CNN) to detect fire/smoke in real-time, providing an efficient alternative to traditional smoke detectors.

## 🚀 Key Features
* **Edge Intelligence:** Runs locally on an MCU (like ESP32-S3) without requiring a cloud connection.
* **Optimized Inference:** Uses **TensorFlow Lite Micro** with 8-bit quantization for low memory consumption.
* **High-Speed Detection:** Specifically tuned to provide inference results in under [X] ms to ensure rapid response.
* **Low False Positives:** Trained on a dataset including "fire-like" backgrounds (sunlight, orange lights) to improve reliability.

## 🛠️ Hardware Requirements
* **MCU:** ESP32-S3 (or any MCU with ~512KB+ SRAM)
* **Camera:** OV2640 or similar camera module
* **Alert System:** (Optional) External Buzzer or LED connected to GPIO.



## 📂 Project Structure
* `/model`: Contains the `.tflite` and the converted C++ byte array (`fire_model_data.h`).
* `/src`: Core C++ logic for image capture and tensor processing.
* `/include`: Configuration for detection thresholds and camera pins.

## ⚙️ Technical Details
* **Model Type:** CNN (Convolutional Neural Network)
* **Input Size:** 96x96 (Grayscale/RGB)
* **Framework:** TensorFlow Lite Micro
* **Quantization:** Full Integer (int8)

## 📊 Performance
| Metric | Result |
| :--- | :--- |
| **Inference Time** | ~150ms (ESP32-S3) |
| **Model Size** | ~250 KB |
| **Accuracy** | 92% (on validation set) |

## ⚡ Quick Start
1. Clone this repository.
2. Ensure you have the **ESP-NN** and **TFLM** libraries installed.
3. Build the project:
   ```bash
   idf.py build
   idf.py flash
