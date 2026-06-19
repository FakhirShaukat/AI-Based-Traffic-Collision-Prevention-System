# AI Multi-Modal Traffic Intelligence System

## Overview

The **AI Multi-Modal Traffic Intelligence System** is an Artificial Intelligence-based traffic management and accident risk prediction system developed as part of an AI Lab project. The system combines **Machine Learning**, **Computer Vision**, **Weather Analysis**, **Search Algorithms**, and **Intelligent Agents** to analyze traffic conditions, estimate accident risk, and recommend the safest route.

The primary objective of the system is to demonstrate how multiple AI techniques can be integrated into a single intelligent framework capable of processing historical accident data, real-time traffic information, and environmental conditions to support safer transportation decisions.

---

## Features

### Historical Accident Analysis

* Uses the US Accidents Dataset.
* Trains Machine Learning models on accident-related features.
* Learns relationships between traffic conditions and accident severity.

### Traffic Density Detection

* Uses YOLOv8 object detection.
* Detects vehicles from traffic video frames.
* Estimates traffic congestion levels in real time.

### Weather Monitoring

* Retrieves visibility and rainfall information using a Weather API.
* Incorporates environmental conditions into accident risk assessment.

### Accident Risk Prediction

* Uses an Artificial Neural Network (ANN).
* Predicts accident probability based on:

  * Traffic density
  * Visibility
  * Rainfall

### Clustering and Classification

* K-Means Clustering groups traffic situations into categories.
* K-Nearest Neighbors (KNN) classifies traffic conditions based on historical patterns.

### Route Optimization

* Simulated road network consisting of:

  * Highway
  * City Road
  * Bypass
* Uses:

  * BFS (Breadth First Search)
  * DFS (Depth First Search)
  * A* Search Algorithm
* Selects the safest route using risk-adjusted cost calculations.

### Driver Warning System

* Generates alerts when accident risk exceeds predefined thresholds.
* Acts as a Simple Reflex Agent.

---

# System Architecture

```text
US Accidents Dataset
        ↓
K-Means + KNN + ANN
        ↓
Learning Agent
        ↓
Accident Risk Prediction

Traffic Video
        ↓
YOLO Vehicle Detection
        ↓
Traffic Density

Weather API
        ↓
Visibility + Rainfall
        ↓
Fuzzy Risk Assessment

Traffic Density + Weather + Historical Learning
                    ↓
            Risk Assessment Engine
                    ↓
          Accident Probability Score
                    ↓
         Simulated Road Network
                    ↓
            BFS / DFS Exploration
                    ↓
             A* Route Selection
                    ↓
            Driver Warning System
```

---

# Technologies Used

## Programming Language

* Python 3.x

## Libraries

### Data Processing

* NumPy
* Pandas

### Machine Learning

* Scikit-Learn

  * KMeans
  * KNeighborsClassifier
  * StandardScaler

### Deep Learning

* TensorFlow
* Keras

### Computer Vision

* OpenCV
* Ultralytics YOLOv8

### Graph Visualization

* NetworkX
* Matplotlib

### API Integration

* Requests

---

# Dataset

## US Accidents Dataset

Source:

[Kaggle US Accidents Dataset](https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents?utm_source=chatgpt.com)

### Features Used

* Severity
* Visibility(mi)
* Precipitation(in)
* Traffic_Signal
* Crossing
* Junction

---

# Input Sources

## Input 1: Historical Accident Dataset

Purpose:

* Train machine learning models.
* Learn accident patterns.

Algorithms:

* K-Means
* KNN
* ANN

---

## Input 2: Traffic Video

Purpose:

* Detect vehicles.
* Estimate traffic density.

Algorithm:

* YOLOv8

Output:

* Number of detected vehicles.

---

## Input 3: Weather API

Purpose:

* Obtain environmental conditions.

Parameters:

* Visibility
* Rainfall

Output:

* Weather-based risk indicators.

---

## Input 4: Simulated Road Network

Purpose:

* Demonstrate graph search algorithms.

Algorithms:

* BFS
* DFS
* A*

Routes:

* Highway
* City Road
* Bypass

---

# Intelligent Agents

## Learning Agent

Implemented using:

* ANN
* KNN
* K-Means

Responsibilities:

* Learn traffic and accident patterns.
* Predict accident risk.

---

## Simple Reflex Agent

Implemented using:

* Driver Warning System

Responsibilities:

* Trigger alerts when risk exceeds threshold.

Example:

```python
if risk > 0.65:
    print("EMERGENCY ALERT")
```

---

## Goal-Based Agent

Implemented using:

* A* Search Algorithm

Responsibilities:

* Select safest route.
* Minimize total route cost.

Cost Function:

```text
f(n) = g(n) + h(n)
```

Where:

* g(n) = actual route distance
* h(n) = risk penalty

---

# Machine Learning Models

## K-Means Clustering

Purpose:

* Group traffic conditions into:

  * Low Traffic
  * Medium Traffic
  * High Traffic

Evaluation Metric:

* Silhouette Score

---

## K-Nearest Neighbors (KNN)

Purpose:

* Classify traffic conditions based on historical accident patterns.

Evaluation Metric:

* Classification Accuracy

---

## Artificial Neural Network (ANN)

Architecture:

```text
Input Layer (3 Features)
        ↓
Dense Layer (16 neurons)
        ↓
Dropout Layer
        ↓
Dense Layer (8 neurons)
        ↓
Output Layer (1 neuron)
```

Input Features:

* Traffic Density
* Visibility
* Rainfall

Output:

* Accident Probability

Evaluation Metrics:

* Loss
* Training Accuracy
* Validation Accuracy

---

# Route Optimization

The system uses a simulated road network to demonstrate graph search algorithms.

Available Routes:

| Route     | Distance (km) |
| --------- | ------------- |
| Highway   | 12.4          |
| City Road | 14.2          |
| Bypass    | 18.5          |

The A* algorithm evaluates each route using:

```text
f(n) = g(n) + h(n)
```

Example:

```text
Highway
g(n) = 12.4
h(n) = 17.48
f(n) = 29.88
```

The route with the lowest total cost is selected.

---

# Sample Output

```text
FRAME 1

Traffic: 30
Risk: 0.28

NORMAL CONDITIONS

Routes:

Highway
g = 12.4
h = 17.48
f = 29.88

City Road
g = 14.2
h = 20.02
f = 34.22

Bypass
g = 18.5
h = 26.08
f = 44.58

Selected Route: Highway
```

---

# Project Workflow

```text
Data Collection
       ↓
Data Preprocessing
       ↓
Model Training
(K-Means + KNN + ANN)
       ↓
YOLO Vehicle Detection
       ↓
Weather Monitoring
       ↓
Risk Assessment
       ↓
Route Evaluation
(BFS + DFS + A*)
       ↓
Driver Warning System
       ↓
Final Recommendation
```

---

# Future Enhancements

* Integration with real Google Maps API.
* Live camera stream support.
* Real-time GPS tracking.
* Advanced deep learning models.
* Smart city traffic infrastructure integration.
* Mobile application deployment.
* Real-time traffic signal management.
* Emergency vehicle prioritization.

---

# Conclusion

This project demonstrates the integration of Machine Learning, Computer Vision, Intelligent Agents, and Search Algorithms into a single AI-driven traffic management framework. The system successfully predicts accident risk, evaluates traffic conditions, and recommends safer routes using a combination of historical accident data, traffic video analysis, weather information, and graph-based route optimization. It serves as a practical example of how AI techniques can be applied to improve transportation safety and support intelligent decision-making in modern traffic systems.
