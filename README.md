# Occupancy and Utilisation Insights for Gartner - DIH

## Overview

This project is a proof-of-concept tool designed to analyze occupancy and group dynamics within Gartner's Sydney office. By leveraging computer vision, IoT devices, and Cisco's infrastructure, the project aims to track and optimize space utilization, understand collaboration patterns, and support data-driven decisions.

The key focus is on integrating computer vision technology to detect and analyze groups, activities, and workspace usage patterns in 15-minute intervals while providing actionable insights through an intuitive dashboard.

## Objectives

### Core Goals
1. *Group Detection and Counting*: Detect and count distinct groups using advanced computer vision techniques.
2. *People Counting in Groups*: Identify the number of individuals within each group.
3. *Zone-Based Analysis*: Divide office space into zones for granular analysis of activities and interactions.
4. *15-Minute Interval Analysis*: Analyze data in short intervals to understand real-time occupancy and group dynamics.
5. *Temporal Insights*: Study trends over longer periods (daily, weekly, monthly) to evaluate workspace performance.
6. *Group Dynamics Analysis*: Provide insights into group formation, interaction, and evolution over time.
7. *Dashboard Visualization*: Develop a user-friendly dashboard for real-time and historical data visualization.

### Nice-to-Have Features
- Advanced image analysis for subjective opinions and open-ended insights.
- Integration with facility management and scheduling systems.
- Predictive analytics for forecasting space utilization trends.

## Key Computer Vision Methodologies

### 1. Group Detection and Counting
- *Bounding Box Proximity*:
  - Calculated distances between bounding box centroids detected by YOLOv8.
  - Applied thresholds to classify individuals into groups based on spatial proximity.

- *Pose-Based Gaze Analysis*:
  - Utilized pose keypoints (e.g., eyes, nose) to determine gaze directions.
  - Intersecting gaze vectors and angle thresholds (≤ 90°) identified interacting individuals.

- *Bounding Box Area Comparison*:
  - Compared bounding box sizes to filter out individuals at varying depths.
  - Mitigated perspective distortion issues in camera views.

- *Graph-Based Grouping*:
  - Modeled individuals as nodes in a graph, with edges based on proximity and gaze criteria.
  - Used graph algorithms to identify distinct groups in real-time.

### 2. Zone-Based Analysis
- Divided the office into 14 distinct zones.
- Analyzed occupancy, group activities, and interactions per zone during each interval.

### 3. Temporal and Interval Analysis
- Collected occupancy and interaction data in 15-minute intervals.
- Aggregated insights to detect temporal trends, such as peak usage times and evolving group dynamics.

## Technologies Used

### Computer Vision
- *YOLOv8*: Object detection and pose estimation for human tracking and group analysis.
- *OpenCV*: For image processing and bounding box visualization.
- *SciPy*: Distance and centroid calculations for bounding box proximity checks.
- *NetworkX*: Graph-based analysis for identifying connected groups.

### Data and Visualization
- *AWS S3*: Cloud storage for captured images and analysis outputs.
- *Power BI*: For creating interactive dashboards and reports.

## Workflow

### Step 1: Data Collection
- *Image Capture*:
  - Connected to IP cameras using RTSP streams.
  - Captured snapshots and uploaded them to AWS S3.
- *Dataset Preparation*:
  - Annotated datasets with bounding boxes and pose keypoints for model training.

### Step 2: Group Detection
1. *Detection*:
   - YOLOv8 detected humans and pose keypoints in each frame.
2. *Grouping Logic*:
   - Calculated proximity and gaze alignment to classify individuals into groups.
   - Filtered out noise using bounding box size comparisons and temporal consistency checks.

### Step 3: Dashboard and Reporting
- *Power BI Visualization*:
  - Displayed group dynamics, zone-level occupancy, and temporal trends.
  - Provided heatmaps, KPIs, and detailed breakdowns for decision-making.

## Challenges and Solutions

### 1. Privacy and Security
- Ensured all data collection was anonymized and compliant with relevant regulations.

### 2. Handling Camera Distortion
- Applied Digital Pan-Tilt-Zoom (DPTZ) corrections to reduce fisheye distortions.

### 3. Occlusions and Crowds
- Fine-tuned YOLOv8 to handle partial occlusions and overlapping individuals.

## Future Enhancements

1. *Predictive Analytics*: Integrate machine learning models to forecast occupancy patterns and optimize space allocation.
2. *Environmental Data Integration*: Incorporate additional data sources such as temperature and noise levels for a holistic view of workspace utilization.
3. *Enhanced Group Interaction Analysis*: Add emotion recognition and behavioral insights to refine group dynamics understanding.

## Getting Started

### Prerequisites
- Python 3.8+
- Installed dependencies (pip install -r requirements.txt)
- Access to IP cameras and AWS credentials.

### Running the System
1. *Data Capture*:
   bash
   python capture_and_upload.py
   
2. *Group Detection*:
   bash
   python group_detection.py
   
3. *Dashboard Visualization*:
   - Import processed data into Power BI.
   - Use the dashboard template for insights.
