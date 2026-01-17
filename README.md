# Vision-Based Hazard Detection and Audio Alert System

## Overview

This project implements a **real-time hazard detection and audio alert system** using computer vision and large language models (LLMs). It is designed to identify obstacles in walking and driving environments and provide **context-aware audio warnings** to improve accessibility and situational awareness.

The system combines **YOLO-World object detection**, **dynamic frame segmentation**, **motion stabilization**, and **LLM-based danger interpretation** to detect hazards and generate spoken alerts in near real time.

This project was developed as part of a Computer Vision course final project.

---

## Key Features

* **Real-time object detection** using YOLOv8x-World (zero-shot capable)
* **Dynamic frame segmentation (H-Split)** to prioritize dangerous regions
* **Motion stabilization** using optical flow to handle camera movement
* **Hazard prioritization** based on object size, location, and frequency
* **LLM-assisted danger interpretation** for contextual risk assessment
* **Audio alerts** generated with text-to-speech when hazards are detected
* Works on both **walking and driving scenarios**

---

## System Architecture

1. **Video Input**
2. **YOLO-World Object Detection**
3. **Motion Stabilization & Frame Segmentation**
4. **Object Prioritization**
5. **Danger Estimation (LLM-assisted)**
6. **Audio Alert Generation**
7. **Annotated Video Output**

---

## Technologies Used

* **Python**
* **YOLOv8x-World**
* **OpenCV**
* **Optical Flow**
* **Large Language Models (LLMs)**
* **gTTS (Google Text-to-Speech)**

---

## Installation

### Prerequisites

* Python 3.9+
* CUDA-capable GPU recommended (CPU supported but slow)

### Clone the Repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Usage

### Run Hazard Detection on a Video

```bash
python main.py --input path/to/video.mp4
```

### Key Parameters

| Parameter     | Description                                         |
| ------------- | --------------------------------------------------- |
| `CONF_THRESH` | Object confidence threshold (recommended: 0.6)      |
| `MIN_AREA`    | Minimum bounding box area ratio (recommended: 0.02) |
| `FRAME_SKIP`  | Frames skipped for performance (recommended: 6)     |

---

## Experimental Results

* Best overall performance achieved with:

  * `CONF_THRESH = 0.6`
  * `MIN_AREA = 0.02`
  * `FRAME_SKIP = 6`
* Average performance: **~14–15 FPS**
* Strong generalization to unseen environments
* More accurate danger detection in **driving scenarios** than walking

---

## Limitations

* High computational cost due to large YOLO and LLM usage
* Occasional false positives in dense environments
* Audio alerts can be overly frequent without further tuning
* No custom-trained YOLO model (zero-shot only)

---

## Future Improvements

* Train a custom YOLO model for specific hazards
* Improve audio alert precision and reduce false positives
* Add traffic light and crosswalk detection
* Optimize LLM usage for lower latency and cost
* Deploy to mobile or wearable devices

---

## Team Contributions

* **Tyler Thach** — Object detection, frame segmentation, stabilization, and text-to-speech
* **Bryan Zavala** — LLM prompt engineering and danger interpretation
* **Kevin Ruvalcaba** — Dataset preparation, evaluation, and presentation design

---

## References

Inspired by:

* *VisionGPT: LLM-assisted Real-Time Anomaly Detection for Safe Visual Navigation*
* *YOLO-World: Real-Time Open-Vocabulary Object Detection*

---

## License

This project is for educational purposes. Licensing can be added if open-sourcing is desired.
