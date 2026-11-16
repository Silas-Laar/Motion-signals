# Motion-signals
Cross-Modal Self-Supervised Representation Learning for Joint Analysis of Wearable Physiological and Motion Signals

Overview

This project develops a cross-modal self-supervised learning framework for learning meaningful representations from multimodal wearable sensor data by integrating electrocardiogram (ECG) signals with inertial measurement unit (IMU) signals.

The framework explores how physiological and motion signals can complement each other during representation learning and investigates whether useful representations can still be learned when certain sensor modalities are unavailable.

Using the MHEALTH dataset, the project evaluates cross-modal representation learning, sensor contribution, and the ability of IMU-only learning to capture useful information without ECG signals.

Research Objectives

Develop a self-supervised framework for learning joint representations from ECG and IMU signals.

Investigate the contribution of different wearable sensor locations to representation quality.

Evaluate whether IMU-only self-supervised learning can produce useful representations without ECG.

Examine the quality of learned representations through downstream classification, visualization, and cross-modal retrieval.

Dataset

The study uses the MHEALTH (Mobile Health) dataset, which contains body motion and physiological recordings collected from wearable sensors.

The dataset includes:

Sensor

Measurements

Chest

3-axis accelerometer

ECG

2 ECG leads

Left ankle

Accelerometer, gyroscope, and magnetometer

Right wrist

Accelerometer, gyroscope, and magnetometer

Sampling frequency: 50 Hz

Number of participants: 10

Number of activity classes: 12, in addition to the null label.

Methodology

1. Data Preprocessing

Load and organize recordings from all 10 participants.

Separate ECG and IMU sensor modalities.

Segment synchronized signals into 5-second windows (250 samples).

Apply 50% overlapping window segmentation.

Split participants into training (subjects 1–8), validation (subject 9), and testing (subject 10) sets.

Exclude null activity windows and apply a window-purity threshold for downstream evaluation.

2. Cross-Modal Self-Supervised Learning

An encoder-based framework learns representations from paired ECG and IMU windows using a contrastive learning objective.

The objective is to bring corresponding cross-modal representations closer while distinguishing non-corresponding samples.

3. Sensor Ablation Experiments

Two experiments investigate the contribution of individual sensor locations:

No-Ankle: Removes left-ankle IMU signals.

No-Wrist: Removes right-wrist IMU signals.

These experiments assess how sensor availability influences learned representations.

4. ECG-Free Representation Learning

An IMU-only self-supervised learning model is trained using independently augmented views of the same motion signal. This evaluates representation learning without relying on ECG measurements.
