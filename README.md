# State Estimation of a Quadrupedal Robot using Temporal Convolutional Networks

## Project Overview
This research investigates the use of **Temporal Convolutional Networks (TCN)** for the accurate state estimation and localization of quadrupedal robots. Unlike traditional wheeled robots, legged locomotion presents unique challenges such as sensor delays, odometry drift on slippery/deformable surfaces, and the repetitive wobbling inherent to walking.

This project leverages proprioceptive data—including joint states (velocity, effort, position) and foot force sensors—to achieve robust real-time localization.

## Key Methodology: PI-TCN
The core of this project is the **Physics-Inspired Temporal Convolutional Network (PI-TCN)** architecture:

* **Feature Encoding (TCN):** A TCN with 5 hidden layers and dilated causal convolutions is used to encode the history of the robot's proprioceptive states.
* **State Prediction (MLP):** A Multilayer Perceptron (MLP) decodes these temporal representations to produce precise predictions of the robot's relative position and orientation.
* **Autoregression:** The model utilizes a batch size of 1 and an autoregressive approach, updating weights after each sample to ensure the next position effectively depends on the preceding state history.

## Technical Stack
* **Deep Learning:** PyTorch, NumPy (custom TCN & MLP architectures)
* **Robotics & Simulation:** ROS (Robot Operating System), Gazebo, Rviz
* **Platform:** Unitree A1 Quadruped Robot
* **Algorithms:** Adam Optimizer, MSE Loss, K-Fold Cross Validation

## Research Problem & Motivation
Standard localization systems like **Visual-Inertial Odometry (VIO)** often fail in textureless environments (ground/sky) or during fast, blurry movements. By focusing on proprioceptive data, this research provides a reliable alternative that surpasses traditional **EKF-based (Extended Kalman Filter)** baselines in challenging terrains where stable footholds cannot be assumed.

---

## 🌐 Portfolio & Contact
This research is part of my professional journey in Machine Learning and Robotics. You can find more details about this project and my other work on my interactive portfolio:

[**Explore my Portfolio**](https://ahmed-moustafa.vercel.app/)