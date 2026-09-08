---
layout: default
title: Projects & Resume
permalink: /projects/
---

# Projects

A collection of projects I've built for learning, experimentation, and the occasional rabbit hole.

## Autonomous Driving & CARLA

I have spent significant time using **CARLA** to learn and experiment with the algorithms and systems that make autonomous driving possible. The simulation environment gave me a way to work with vehicle dynamics, cameras, LiDAR and other simulated sensors while building the perception, localization, planning, and control pieces around them.

A large part of this work was learning how the mathematics and algorithms behind autonomous systems fit together in practice. Some of the topics I studied and implemented included:

* **Kalman Filtering** for estimating vehicle state from noisy sensor measurements.
* **Bayes' Theorem and Probabilistic Robotics** for reasoning about uncertain observations and beliefs about the vehicle's state and environment.
* **Particle Filters / Monte Carlo Localization** for estimating position when the system has uncertainty and nonlinearities that make simpler approaches insufficient.
* **SLAM (Simultaneous Localization and Mapping)** for building a representation of the environment while simultaneously estimating the vehicle's location within it.
* **Homogeneous Transformations** for representing and transforming positions and orientations between coordinate frames, an essential part of working with multiple sensors and vehicle geometry.
* **Vision Transformers (ViTs)** and **BEVFormer-style architectures** for learning about modern vision-based perception and bird's-eye-view representations of the driving environment.
* **Dijkstra's algorithm** for graph-based path planning and finding shortest paths through a representation of the environment.
* **Model Predictive Control (MPC)** for vehicle trajectory tracking and control while considering the vehicle's dynamics and future state.

What I found particularly interesting was seeing how these pieces connect. Sensor measurements become estimates through filtering and probabilistic reasoning; coordinate transformations allow those measurements to be combined; perception produces an understanding of the surrounding environment; localization determines where the vehicle is within that environment; planning determines where it should go; and control algorithms such as MPC turn that plan into actual vehicle motion.

CARLA made it possible to experiment with this entire pipeline in a controlled environment and to see how changes in one part of the system propagate through the rest of the autonomy stack.

## For Fun & Learning

A collection of smaller projects and experiments covering software, hardware, automation, and whatever else I happen to be interested in.

[**ForFun →**](https://github.com/RParkerE/ForFun)

## Monkey Business

Projects and experiments based on Thorston Bell's books, exploring programming and problem solving through the exercises and ideas presented there.

[**MonkeyBusiness →**](https://github.com/RParkerE/MonkeyBusiness)

## LLM Learning

An ongoing project where I am learning about large language models by working through the concepts and implementations from first principles rather than treating them as black boxes.

[**LLM-Learning →**](https://github.com/RParkerE/LLM-Learning)

## GetPopTimesAPI

A deprecated project that experimented with scraping Google Places busyness information.

[**GetPopTimesAPI →**](https://github.com/RParkerE/GetPopTimesAPI)

## Magic Lamp

An Arduino project that controls a lamp based on local sunrise and sunset times, using IP-based location information to determine when it should turn on and off.

[**MagicLamp →**](https://github.com/RParkerE/MagicLamp)

## Heart Rate Monitor

A collection of Python scripts for the BeagleBone Black and Raspberry Pi that collect readings and display heart-rate information.

[**HeartRateMonitor →**](https://github.com/RParkerE/HeartRateMonitor)

---

More projects will make their way here as I build them.
