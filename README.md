# Fire Detection Using Computer Vision (YOLOv8)

## About

This project implements an object detection model trained using YOLOv8s for fire detection with computer vision. The model is built on a self-curated and manually labeled dataset and goes beyond the traditional “fire vs no fire” classification. Instead, it detects fires based on severity, allowing the system to differentiate between hazardous fires that require urgent attention and visually present but relatively safe fires. The goal is to reduce false alarms while still reliably identifying dangerous situations where intervention is critical.

---

## Motivation

Traditionally, heat sensors are used for fire detection in say, fire alarms, but they also have constraints like needing a closed structure or requiring Infrared Cameras. Computer Vision models can be readily deployed on existing cameras, with the main concern being reducing False Positives. 

Most fire detection models treat all fires as equally dangerous, which can lead to unnecessary alerts in real-world deployments. In practice, a controlled flame such as a candle, campfire, or small contained burn does not pose the same risk as an aggressive, spreading fire in an urban or industrial environment. This project was motivated by the need to incorporate contextual and visual severity cues into fire detection so that automated systems can make more informed decisions.

---

## Dataset

The dataset used in this project was **collected and labeled manually**. Images were categorized into three classes:

* **fire**: Controlled or contained fires that do not pose immediate risk.
* **HZRD**: Fires that are visually aggressive, irregular, wide-spreading, or contextually dangerous.
* **No Fire**: Scenes without visible fire.

During annotation, special attention was paid to visual cues such as fire shape, spread, intensity, and surrounding environment. Hazardous fires often appear “out of shape,” meaning they are chaotic, disproportionate to their setting, or visually violent, and this concept was intentionally incorporated into the labeling process. The dataset is organized in a class-wise folder structure and is designed to be easily extendable.

---

## Model and Approach

* **Model**: YOLOv8s (Ultralytics)
* **Framework**: PyTorch
* **Task**: Object detection with severity-aware classification

YOLOv8 was chosen because of it's fast inference, suitability for real-time applications and better performance for this type of model. The model learns visual patterns associated to the shape of the fire and surrounding visual cues.

---

## Inference

The trained model supports real-time inference, batch inference on folders of images as well as image-by-image inspection. Confidence thresholds can be adjusted to control sensitivity, and prediction outputs can be saved for visualization and evaluation.

---

## Results and Observations

The model is able to:

* Detect fire reliably in diverse environments
* Distinguish hazardous fires from visually mild or controlled fires
* Reduce false positives compared to simple fire/no-fire approaches

Failure cases and ambiguous scenarios are retained for future dataset refinement.

---

## Project Structure

```      
├── dataset/
├── models/
├── inference/
├── assets/
├── README.md
```

---

## Tech Stack

Python, PyTorch, YOLOv8 (Ultralytics), Roboflow, Computer Vision

---

## Future Work

* Expand dataset diversity and size
* Introduce distance estimation
* Integration with Infrared footage
* Web or mobile deployment for monitoring applications

