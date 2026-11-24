# 🤖 Edge AI-Based IoT Intrusion Detection System

An AI-powered IoT Intrusion Detection System that uses Machine Learning, Edge Computing, and MQTT communication to monitor IoT network traffic and identify potentially malicious activities in real time.

The project integrates a Random Forest classification model with an ESP32-based IoT simulation, MQTT messaging, and a Flask-based monitoring dashboard to demonstrate intelligent network security for connected IoT environments.

## 🚀 Overview

The **Edge AI-Based IoT Intrusion Detection System** is designed to identify abnormal network behavior and detect potential cyberattacks in IoT environments using Machine Learning.

The system simulates multiple smart devices, collects their network activity, and analyzes traffic patterns using a trained Random Forest classifier.

It demonstrates how AI-powered edge security systems can help monitor IoT environments and identify suspicious network activities without relying entirely on traditional rule-based detection mechanisms.

The platform combines:

- Machine Learning-based intrusion detection
- IoT device simulation using ESP32
- MQTT-based communication
- Edge AI processing
- Network traffic monitoring
- Flask-based web application
- Attack and normal traffic classification

## 💡 Problem Statement

The increasing use of Internet of Things (IoT) devices has introduced several network security challenges.

Connected devices are vulnerable to different types of cyberattacks, including:

- Denial-of-Service (DoS) attacks
- Abnormal network traffic
- Unauthorized communication
- Suspicious connection activities
- Malicious traffic patterns

Traditional security mechanisms may struggle to identify changing attack patterns in dynamic IoT environments.

Therefore, an intelligent intrusion detection system is required to monitor network behavior and identify potential threats efficiently.

## 🎯 Proposed Solution

The proposed system uses Machine Learning and Edge Computing to analyze IoT network traffic and classify it as either **NORMAL** or **ATTACK**.

A Random Forest classifier is trained using an IoT network traffic dataset. The trained model is integrated with a Python-based MQTT gateway that receives data published by the ESP32 IoT simulation.

The system processes incoming data, extracts relevant network features, and generates predictions using the trained model.

A Flask-based web application provides an interface for monitoring and interacting with the intrusion detection system.

## ✨ Features Implemented

### 🤖 1. AI-Based Intrusion Detection

- Random Forest classification algorithm.
- Machine Learning-based network traffic analysis.
- Identification of normal and suspicious traffic.
- Prediction using extracted network features.
- Confidence-based prediction output.

### 🌐 2. IoT Device Simulation

The project uses an ESP32-based IoT simulation through Wokwi.

The simulated environment includes:

- Smart Light
- Smart Thermostat
- Smart Camera
- Smart Lock
- Smart Meter
- ESP32 IoT Gateway

The simulation generates normal and abnormal network conditions to demonstrate the behavior of an IoT environment under different traffic conditions.

### 📡 3. MQTT Communication

MQTT is used as the messaging protocol between the IoT simulator and the Python-based Edge AI Gateway.

Implemented functionality:

- MQTT message publishing.
- MQTT message subscription.
- JSON-based IoT data transmission.
- Device data reception.
- Integration with the Machine Learning prediction system.

**MQTT Topic:**
`edge_ai_ids/abhi_esp32_iot_data`

### 🧠 4. Edge AI Gateway

The Python MQTT Edge Gateway connects the IoT simulation with the trained Machine Learning model.

Its responsibilities include:

- Connecting to the MQTT broker.
- Receiving IoT device messages.
- Extracting relevant information.
- Converting incoming data into model-compatible features.
- Running Random Forest predictions.
- Classifying traffic as NORMAL or ATTACK.
- Displaying prediction results and confidence scores.

### 📊 5. Network Traffic Monitoring

The system maintains records of network traffic and intrusion-related activities.

The project includes:

- Traffic logging.
- Intrusion logging.
- Normal and attack traffic records.
- Device activity monitoring.
- CSV-based log storage.

### 🖥️ 6. Flask-Based Web Application

The project includes a Flask-based web interface for interacting with the intrusion detection system.

The application is developed using HTML, CSS, JavaScript, and Python Flask.

### 🔍 7. Machine Learning Model Validation

The trained Random Forest model was tested using sample normal and attack traffic inputs.

Observed test results:

- Normal traffic test → NORMAL
- High-volume attack traffic test → ATTACK

These tests verify that the trained model loads successfully and produces the expected classifications for the tested examples.

## 🛠️ Tech Stack

### Programming Languages
- Python
- C/C++ (ESP32 Arduino programming)
- HTML5
- CSS3
- JavaScript

### Artificial Intelligence & Machine Learning
- Scikit-learn
- Random Forest Classifier
- Pandas
- NumPy
- Joblib

### Internet of Things
- ESP32
- Wokwi Simulator
- Arduino CLI

### Communication Protocol
- MQTT
- Paho MQTT
- JSON

### Backend Development
- Flask
- Python

### Frontend Development
- HTML
- CSS
- JavaScript

### Data Visualization
- Matplotlib

### Development Environment
- Visual Studio Code
- Python Virtual Environment
- PowerShell
- Git
- GitHub

## 📁 Project Structure

```text
Edge_AI_IDS/
│
├── dataset/
│   ├── iot_traffic.csv
│   └── processed_iot_traffic.csv
│
├── logs/
│   ├── traffic_log.csv
│   └── intrusion_log.csv
│
├── static/
│   ├── css/
│   └── js/
│
├── templates/
│
├── venv/
│
├── app.py
├── data_preprocessing.py
├── edge_gateway.py
├── intrusion_model.pkl
├── mqtt_edge_gateway.py
├── mqtt_publish_test.py
├── mqtt_test.py
├── traffic_generator.py
├── train_model.py
└── wokwi_mqtt_receiver.py
```

**Wokwi IoT Simulation (separate project folder):**

```text
Wokwi_IoT_Simulation/
│
├── build/
├── diagram.json
├── libraries.txt
├── wokwi.toml
└── Wokwi_IoT_Simulation.ino
```

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/Edge_AI_IDS.git
```

### 2. Navigate to the Project Directory

```bash
cd Edge_AI_IDS
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

### 4. Activate the Virtual Environment

**Windows PowerShell:**

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\venv\Scripts\Activate.ps1
```

### 5. Install Dependencies

```bash
python -m pip install flask pandas numpy scikit-learn joblib matplotlib paho-mqtt
```

### 6. Run the Flask Application

```bash
python app.py
```

Open the application in your browser:

```text
http://127.0.0.1:5000
```

### 7. Run the MQTT Edge Gateway

In a separate terminal, activate the virtual environment and navigate to the project directory.

Run:

```bash
python mqtt_edge_gateway.py
```

The gateway connects to the configured MQTT broker and subscribes to the IoT simulation topic.

### 8. Start the IoT Simulation

Open the separate `Wokwi_IoT_Simulation` project.

Compile the ESP32 sketch using:

```bash
arduino-cli compile --fqbn esp32:esp32:esp32 --output-dir .\build .
```

Start the Wokwi simulation and verify that the ESP32 publishes MQTT messages.

**Important:** The MQTT broker configuration and topic must match between the ESP32 simulation and the Python MQTT gateway.

## 📊 System Workflow

The system follows the workflow below:

**Step 1 – IoT Device Simulation**

ESP32 simulates multiple smart devices and generates device activity.

**Step 2 – Data Publishing**

IoT data is converted into JSON messages and published through MQTT.

**Step 3 – MQTT Communication**

The Python MQTT Edge Gateway subscribes to the configured topic and receives the messages.

**Step 4 – Feature Extraction**

Incoming IoT information is converted into the features required by the trained Random Forest model.

**Step 5 – AI-Based Classification**

The Machine Learning model analyzes the input and predicts whether the traffic is NORMAL or ATTACK.

**Step 6 – Monitoring and Logging**

Traffic and intrusion-related information can be recorded for monitoring and further analysis.

## 🧠 Machine Learning Model

The project uses a **Random Forest Classifier** for IoT intrusion detection.

The model works with the following input features:

- Packet Size
- Packets Per Second
- Number of Connections
- Duration
- IoT Device Information
- Communication Protocol

The device and protocol information is represented using encoded features.

The model generates a classification:

- NORMAL – Traffic classified as normal.
- ATTACK – Traffic classified as potentially malicious.

The model is stored in a serialized `.pkl` file and loaded by the Python application using Joblib.

## 🔐 Security Applications

The project demonstrates the application of AI-based security in IoT environments through:

- Continuous IoT traffic monitoring.
- Identification of abnormal network behavior.
- Machine Learning-based threat classification.
- Monitoring of suspicious traffic patterns.
- Centralized traffic and intrusion records.

## 📌 Future Improvements

The following features can be explored in future versions:

- Advanced attack-type classification.
- Improved real-time intrusion detection.
- Automated threat response and device isolation.
- Model performance analytics.
- Additional Machine Learning algorithms.
- Enhanced IoT device authentication.
- Deployment on physical ESP32 hardware.
- Lightweight edge deployment and optimization.
- Advanced security monitoring and reporting.
- Cloud-based IoT security monitoring.

## 🎓 Learning Outcomes

Through this project, I developed practical knowledge of:

- Machine Learning and Random Forest classification.
- IoT architecture and ESP32 programming.
- MQTT communication protocols.
- Edge Computing concepts.
- Network traffic analysis.
- Intrusion detection techniques.
- Flask application development.
- Python-based AI integration.
- Real-time data communication.
- Integration of IoT and Artificial Intelligence.

## 🌍 Real-World Applications

The proposed system demonstrates concepts that can be applied in:

- Smart Home Security
- Industrial IoT Monitoring
- Smart Building Networks
- Connected Healthcare Systems
- Industrial Automation
- IoT Network Security Monitoring

## 📬 Contact

**Developer:** Srishti S Rao

**Degree:** B.Tech – Electronics and Computer Engineering (AI/ML Specialization)

**Institution:** Christ University (Deemed to be University)

**Location:** Bengaluru, India

- Email: srishtisrao26@gmail.com
- LinkedIn: https://www.linkedin.com/in/srishti-s-rao-b09189316
- GitHub: https://github.com/srishtii26

---

⭐ If you find this project interesting, consider giving the repository a star!

**Developed with a focus on Artificial Intelligence, Edge Computing, IoT, and Cybersecurity.**
