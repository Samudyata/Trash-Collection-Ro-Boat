# Trash Collection Ro-Boat -- Autonomous Aquatic Cleanup Robot

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-3B-C51A4A?style=for-the-badge&logo=raspberry-pi&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-Image%20Processing-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Classification-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)

An autonomous, low-cost aquatic robot designed to detect, collect, and manage surface trash from water bodies using image processing, smart sensors, and IoT-enabled navigation. Built as a capstone project to address the growing problem of water pollution from plastics and non-biodegradable waste.

---

## System Architecture

```
                         +-------------------+
                         |   Raspberry Pi    |
                         |   3B (Controller) |
                         +--------+----------+
                                  |
            +---------------------+---------------------+
            |                     |                     |
            v                     v                     v
   +--------+--------+  +--------+--------+  +---------+--------+
   |   Pi Camera     |  |  Motor Control  |  |   Sensor Suite   |
   |   + OpenCV      |  |  (GPIO + PWM)   |  |                  |
   +--------+--------+  +--------+--------+  +---------+--------+
            |                     |                     |
            v                     v                     v
   +--------+--------+  +--------+--------+  +---------+--------+
   | Trash Detection  |  | BLDC Motors     |  | PIR Sensor       |
   | & Classification |  | (propulsion)    |  | (organism detect)|
   | (TensorFlow)     |  | Servo Motors    |  | Load Cell        |
   |                  |  | (steering)      |  | (bin capacity)   |
   |                  |  | Stepper Motors  |  |                  |
   |                  |  | (collection)    |  |                  |
   +------------------+  +-----------------+  +------------------+
```

---

## Hardware Components

| Component | Purpose | Specification |
|-----------|---------|---------------|
| **Raspberry Pi 3B** | Main controller | 1.2 GHz quad-core ARM Cortex-A53, 1 GB RAM |
| **Pi Camera** | Trash detection | 5 MP camera module |
| **BLDC Motors** | Propulsion | Forward/backward movement |
| **Servo Motors** | Navigation | Directional steering |
| **Stepper Motors** | Collection | Trash pickup mechanism |
| **PIR Sensor** | Safety | Living organism detection and avoidance |
| **Load Cell** | Monitoring | Bin weight measurement for capacity tracking |
| **LiPo Battery** | Power supply | Rechargeable lithium polymer |
| **Pool Noodles** | Flotation | Buoyancy and stability |

---

## Software Stack

| Component | Technology |
|-----------|------------|
| **Operating System** | Raspberry Pi OS |
| **Programming Language** | Python 3 |
| **Image Processing** | OpenCV |
| **Object Classification** | TensorFlow |
| **Motor Control** | GPIO + PWM via `machine` module |

---

## How It Works

1. **Detection** -- The Pi Camera continuously scans the water surface; OpenCV processes frames to detect floating objects.
2. **Classification** -- TensorFlow classifies detected objects as trash or non-trash. The PIR sensor identifies living organisms to avoid.
3. **Navigation** -- BLDC motors propel the boat toward detected trash; servo motors handle directional steering.
4. **Collection** -- Stepper motors operate the trash pickup mechanism, collecting items into the onboard bin.
5. **Capacity Monitoring** -- A load cell tracks bin weight. When the threshold is reached, the boat navigates to the nearest bank.
6. **Large Item Handling** -- Objects too large for the bin are pushed to the nearest bank by the boat itself.
7. **Auto-Docking** -- Once the bin is full, the boat returns to a designated bank location to offload collected trash.

---

## Cost Analysis

| | Our Design | Commercial Equivalent |
|--|-----------|----------------------|
| **Cost** | Rs 9,490 | Rs 41,000 |
| **Savings** | **77% cheaper** | -- |

The modular design keeps costs low while maintaining all core functionality for effective aquatic trash collection.

---

## Key Achievements

- Accurate real-time trash detection on water surfaces
- Successful identification and avoidance of living organisms
- Smart routing and autonomous navigation
- Cost-effective and modular design at a fraction of commercial solutions

---

## Future Work

- **Deep learning upgrade** -- Replace basic classification with YOLOv5 for real-time multi-class object detection
- **Solar recharge** -- Add solar panels for energy-independent extended operation
- **Multi-trash classification** -- Categorize collected waste (plastics, metals, organic)
- **Remote monitoring** -- Build a mobile/web dashboard for real-time fleet tracking and control

---

## Documentation

The full capstone report is available in the repository: [`CAPSTONE.pdf`](./CAPSTONE.pdf)

---

## Project Structure

```
Trash-Collection-Ro-Boat/
|-- README.md          # Project documentation
|-- CAPSTONE.pdf       # Full capstone project report
|-- .gitignore         # Git ignore rules
```

---

## Author

**Samudyata Jagirdar**

---

## License

This project is intended for educational and research purposes.
