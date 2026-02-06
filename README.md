# Furuta Pendulum Simulation

This repository contains a Python-based simulation of the **Furuta Pendulum** (rotary inverted pendulum) using **MuJoCo**. The project demonstrates both swing-up control and stabilization of the pendulum, providing a testbed for control algorithms and reinforcement learning experiments.

LQR (Linear Quadratic Regulator) is used to stabilize the Furuta Pendulum near its upright position. It computes the optimal torque by minimizing deviations from the target state while keeping control effort small. By linearizing the pendulum dynamics around the upright point, LQR provides a simple yet efficient way to balance the pendulum. This makes it ideal for combining with a swing-up controller to achieve full control from hanging to upright.

---

![mujuco_furuta_pendulum](https://github.com/user-attachments/assets/34fe1037-a293-4439-8590-4e9fed6ec0e4)



<img width="1920" height="770" alt="Furuta_pendulum v1" src="https://github.com/user-attachments/assets/a66966b5-3ff7-4e01-aa8e-b03947a9b0e6" />


## Features

- Swing-up and stabilization controller for the Furuta Pendulum
- Real-time simulation with **MuJoCo**
- Torque control and damping feedback for stable upright balancing
- Visualization using `mujoco.viewer`
- Easy-to-modify parameters for learning and experimentation

---

## Requirements

- Python 3.10+
- [MuJoCo](https://mujoco.org/) (and license)
- `mujoco` Python bindings
- `numpy`
- `time`

Install Python dependencies via pip:
```bash
pip install mujoco numpy
```

## Usage

1. Clone the repository:
```bash
git clone https://github.com/le-nicolas/furuta-pendulum.git
cd furuta-pendulum
```

2. Run the simulation
``` bash
python furuta_control_lqr.py
```

3. Observe the pendulum swing up and balance

---

## Files
* furuta_control_lqr.py - Main simulation script
* furuta_pendulum2.xml - MuJoCo model of the Furuta pendulum

## Control Explanation

The pendulum controller consists of:

> Swing-up control: gradually increases energy to bring the pendulum close to upright

> Balancing control: once near the upright position, a linear feedback stabilizes it

> Damping feedback: prevents drift of the arm and improves stability

You can tune the gains in controller.py to see different behavior.

---
## References
* MujoCo Documentation
* Furuta, K. (1992). “Rotary Inverted Pendulum: Dynamics and Control.”
