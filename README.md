🎾 AcePose: Tennis Pose Recognition Using Deep Learning
AcePose is a computer vision model built to recognize tennis poses—specifically distinguishing between backhand, forehand, serve, and ready position—from single-frame RGB images. The model leverages deep learning with Grad-CAM-based visualization to offer explainable predictions, making it both effective and interpretable.

📌 Table of Contents
Demo

Project Highlights

Model Performance

Visualizations

Dataset

How It Works

Installation & Usage

Libraries Used

Advantages

Limitations

Future Work

🎥 Demo
Below are sample visualizations generated using Grad-CAM to highlight the model’s focus:

<img src="/Images/prediction 1.png" width="800"/> <img src="/Images/serve.png" width="800"/>

🚀 Project Highlights
Task: Classify a tennis player's pose from static images.

Classes: backhand, forehand, serve, ready_position

Model Architecture: CNN (details in AcePose.ipynb)

Explainability: Grad-CAM overlays to interpret predictions

Evaluation Metrics: F1 Score, Loss Curves, Visual Misclassifications

📈 Model Performance
📊 F1 Score & Loss Curves
<img src="/Images/f1 score curves.png" width="800"/> <img src="/Images/loss curves.png" width="800"/>
Epoch	Train Loss	Val Loss	Train F1	Val F1
1	1.0240	0.4389	0.7281	0.8750
2	0.1630	0.0771	0.9456	0.9700
3	0.0444	0.1455	0.9850	0.9550
4	0.0689	0.2611	0.9775	0.9350
5	0.0388	0.1888	0.9850	0.9500

Best validation F1 score: 0.9700 (Epoch 2)

📊 Visualizations
🎯 Class Distribution
<img src="/Images/Testing Distributioon.png" width="800"/>
Balanced dataset across all classes (backhand, forehand, serve, ready_position)

🗂 Dataset
The dataset was sourced from a curated collection of tennis images featuring various player poses. It includes high-resolution frames with clear visibility of player stance and racket position.

Training Samples: ~400 per class

Validation Samples: ~50 per class

Testing Samples: ~50 per class

All images were resized and augmented (horizontal flip, brightness adjustment) during preprocessing.

⚙️ How It Works
Input: RGB image of a tennis player mid-action

Preprocessing: Resize, normalize, apply transforms

Model Prediction: CNN outputs class probabilities

Postprocessing: Top-1 class selected

Grad-CAM: Overlay created to visualize which areas influenced the prediction

🛠 Installation & Usage
🔧 Setup
bash
Copy
Edit
git clone https://github.com/yashwalker7/AcePose.git
cd AcePose
pip install -r requirements.txt
▶️ Run Notebook
Open and run AcePose.ipynb in Jupyter or Colab.

📦 Libraries Used
torch, torchvision — Model architecture, training

matplotlib, seaborn — Visualization

sklearn — Metrics (F1 Score, confusion matrix)

opencv — Image manipulation

PIL — Image loading

grad-cam — Model explainability (optional lib or custom implementation)

✅ Advantages
✅ Highly interpretable results using Grad-CAM

✅ Consistently high F1 scores (>0.95)

✅ Well-balanced dataset across classes

✅ Lightweight and fast (trained in <10 epochs)

✅ Customizable and extensible for other sports/poses

⚠️ Limitations
❌ Some confusion between similar poses (e.g. serve vs ready_position)

❌ Model might be biased by background cues if not properly regularized

❌ Performance may degrade on non-tennis courts or with occlusions

🔮 Future Work
Fine-tuning on edge cases (e.g. occluded hands)

Support for video sequences (pose detection over time)

Deploy via Flask or Streamlit for live demo

Include pose keypoint estimation using OpenPose or Mediapipe
