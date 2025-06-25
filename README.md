# Needle in the Haystack: Robotic Sorting System (Webots Simulation)

A simulation of a robotic arm that automates object classification and sorting tasks using vision and sensor data. Built in the Webots simulation environment, the project replicates a real-world quality control scenario where a robotic arm identifies and isolates a single “odd” item from a set of standardized objects on a conveyor belt.

---

## 🧠 Project Summary

The goal of this system is to simulate a robotic sorting arm that locates and removes an outlier object based on color. Using Webots, C programming, and hardware-like sensors (RGB camera, distance sensor, joint sensors), the system performs a cycle of detecting, picking, and sorting cubes—until it finds the object that doesn't match the rest.

---

## 🔧 System Design

### Robot Setup:
- **4 DOF robotic arm** with actuated joints
- **3-finger gripper** for object grasping
- **RGB camera** for color detection
- **Distance sensor** to detect object proximity
- Controlled using Webots' `motor` and `sensor` APIs

### Environment:
- Objects placed on a **moving conveyor belt**
- Simulation includes barriers, crates, and a holding zone
- Cubes are either **green**, **pink**, or a third **odd** color

### Control Logic:
Implemented via a **finite state machine** with five stages:

1. **WAIT** – Wait for object detection using distance sensor  
2. **GRAB** – Activate gripper to pick up object  
3. **ROTATE** – Move based on object color: sort green/pink or isolate odd item  
4. **DROP** – Release object into appropriate crate  
5. **RETURN** – Reset arm to home position and repeat  

---

## 📷 Visualization & Output

- Color detection handled via RGB thresholding from camera input
- Terminal `printf` logs show current state, detected color, and joint angles
- Visual feedback helps track robot behavior and debug issues during runtime

---

## 🧪 Challenges & Learnings

### ✖️ Challenges
- Inconsistent object dropping due to release timing/calibration  
- Angle-dependent pickup issues for misaligned objects  
- Glitching at conveyor edge and object clipping into environment  
- Gripper occasionally released objects too early

### ✅ Lessons Learned
- Integrated and debugged a state-driven robotic controller  
- Tuned gripper and joint movement for better precision  
- Understood sensor-actuator coordination in simulated robotics  
- Learned limitations of simulated environments vs. real hardware

---

## 🔄 Suggested Future Improvements

- Rewrite controller in **Python** to integrate **PyTorch** for better object recognition  
- Add depth sensing or object alignment aids to improve pickup reliability  
- Calibrate gripper release position and delay logic  
- Modify conveyor layout to prevent end-of-belt object jamming  
- Use barriers or auto-align mechanisms to reduce manual resets

---

## 🎯 Outcome

This project successfully simulates a robotic sorting system capable of identifying and isolating anomalous items based on visual input. While there were physical limitations and areas for refinement, it demonstrates how vision, sensors, and autonomous logic can combine to solve repetitive industrial tasks.

---

## 🛠 Technologies Used

- Webots (robotics simulation)
- C programming
- RGB camera & distance sensors
- Finite state machine logic
- Cyberbotics documentation & tutorials

---

## 👤 Author

**Asif Hussain**  
🌐 [asifh.me](https://asifh.me/work/Robotics)

---

## 📝 License

MIT License (suggested for educational and open-source use)
