Office Occupancy and Utilization Insights
A cutting-edge solution leveraging computer vision and data visualization to optimize workspace usage and enhance operational decision-making.

Key Features
Advanced Detection: Accurate identification of individuals and groups using YOLOv8, bounding box proximity, area ratios, and pose estimation.
Dynamic Adaptability: Parameter tuning for varying camera angles and perspectives, ensuring reliable results across scenarios.
Comprehensive Analytics: Real-time density heatmaps visualizing occupancy patterns.
Power BI Integration: Actionable dashboards for workspace utilization insights, powered by Cisco Meraki camera data.

Demo Outputs
Person and Group Detection

Occupancy Heatmap

Power BI Dashboard

Getting Started
Installation
Clone the Repository

bash
Copy code
git clone https://github.com/your-username/office-occupancy.git
cd office-occupancy
Install Dependencies

bash
Copy code
pip install -r requirements.txt
Prepare Input Data

Place images in the test/ folder for analysis.
Usage
Run Detection

bash
Copy code
python detect.py
Outputs

Detection Results: Saved as group_detection_output.jpg.
Density Heatmap: Saved as density_heatmap.jpg.
Run Logs: Found in the runs/detect/predict/ folder, tracking detection history and metrics.
Project Structure
plaintext
Copy code
office-occupancy/
│
├── test/                # Folder for input images
├── runs/detect/predict/ # Folder for detection outputs and logs
├── detect.py            # Main detection script
├── utils.py             # Helper functions
├── requirements.txt     # Required Python libraries
├── assets/              # Images for README
└── README.md            # Documentation
Technologies Used
Computer Vision: YOLOv8 for detection and YOLOv8-Pose for pose estimation.
Programming: Python (OpenCV, NumPy, SciPy, Matplotlib).
Visualization: Power BI for interactive dashboards.
Hardware Integration: Cisco Meraki cameras for data capture.
Results and Insights
Accurate Detection: Robust grouping and individual identification using bounding box proximity, area ratios, and pose features.
Dynamic Scalability: Easily adapts to various office setups and camera configurations.
Actionable Data: Dashboards enabling better workspace planning and decision-making.
Collaborators and Acknowledgments
Korus Australia and Cisco for collaborative efforts and support.
La Trobe University for facilitating the development of this project.
License
This project is licensed under the MIT License. See the LICENSE file for details.

Contact
Feel free to reach out for queries or contributions:
[Your Name]

GitHub: your-username
Email: your-email@example.com
