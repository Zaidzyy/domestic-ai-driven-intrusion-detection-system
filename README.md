# Domestic AI-driven Intrusion Detection System

## 🚀 Overview
This project is a lightweight, AI-enhanced Intrusion Detection System (IDS) designed to monitor network traffic on your home Wi-Fi network. It uses machine learning to flag unusual or potentially malicious activity in real time, with a modern dashboard and optional threat intelligence and auto-blocking features.

![Demo Image](/app_image.jpg)

---

## 🧰 Features
- **Real-time Packet Sniffing:** Captures live network traffic using Scapy.
- **Feature Extraction:** Extracts protocol, source/destination, and packet size features.
- **Machine Learning Detection:** Classifies traffic as normal or suspicious using a Random Forest model.
- **Threat Intelligence:** Integrates with AbuseIPDB to check IP reputation.
- **Auto-Blocking:** Automatically blocks high-risk IPs using firewall rules (Windows only).
- **Interactive Dashboard:** Streamlit dashboard for live traffic, alerts, and threat intelligence.
---

## 📦 Project Structure
```
.
├── data/                # Datasets, logs, and captured packets
├── models/              # Trained ML models and encoders
├── src/                 # Source code (sniffer, ML, detection, threat intel)
├── dashboard/           # Streamlit dashboard app
├── requirements.txt     # Python dependencies
└── README.md            # This file
```

---

### 1. Clone the Repository
```sh
git clone https://github.com/Zaidzyy/domestic-ai-driven-intrusion-detection-system
cd domestic-ai-driven-ids
```

### 2. Set Up the requirements
```sh
pip install --upgrade pip
pip install -r requirements.txt
```

### 3. Prepare Dataset & Train Model
```sh
python src/dataset_prep.py      # Download and preprocess NSL-KDD
python src/train_model.py       # Train and save the ML model
```

### 4. Start Packet Capture
```sh
python src/sniffer.py           # Run in a separate terminal
```

### 5. (Optional) Set AbuseIPDB API Key
Get a free API key from [AbuseIPDB](https://www.abuseipdb.com/).
```sh
$env:ABUSEIPDB_API_KEY="your_api_key_here"  # Windows
export ABUSEIPDB_API_KEY="your_api_key_here"  # Linux/Mac
```

### 6. Run Real-Time Detection
```sh
python src/realtime_detect.py   # Run in a separate terminal
```

### 7. Launch the Dashboard
```sh
streamlit run dashboard/app.py
```
Visit [http://localhost:8501](http://localhost:8501) in your browser.

---

## 🔒 Security & Ethics
- **For home/lab use only.**
- **Auto-blocking** can disrupt your network if misused—use with caution.
- **Do not use on networks you do not own or have permission to monitor.**

---

## 🙏 Acknowledgements
- [Scapy](https://scapy.net/)
- [scikit-learn](https://scikit-learn.org/)
- [Streamlit](https://streamlit.io/)
- [AbuseIPDB](https://www.abuseipdb.com/)
- [NSL-KDD Dataset](https://www.unb.ca/cic/datasets/nsl.html) 
