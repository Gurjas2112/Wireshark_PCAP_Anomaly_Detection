# Wireshark PCAP Anomaly Detection

An AI-based tool to analyze network packet captures for anomalies using machine learning techniques. Upload a PCAP file captured from Wireshark to identify potential security issues, network misconfigurations, or unusual traffic patterns.

## 🔍 Overview

This tool provides comprehensive network traffic analysis by leveraging Isolation Forest machine learning algorithms to detect anomalous behavior in packet captures. It offers detailed insights into TLS patterns, protocol distributions, and potential security threats.

## ✨ Features

- **Automated Anomaly Detection**: Uses Isolation Forest ML algorithm to identify suspicious network patterns
- **Multiple Extraction Methods**: Supports both PyShark and tshark for packet analysis with automatic fallback
- **Comprehensive Analysis**:
  - Protocol distribution analysis
  - TLS traffic deep-dive
  - Packet timeline visualization
  - Source/destination IP frequency analysis
  - Communication pattern detection
- **Anomaly Classification**:
  - High/Low packet length detection
  - TCP retransmission identification
  - Reset flag detection
  - TLS fragmentation analysis
  - Potential DoS pattern detection
  - Unusual HTTP traffic detection
  - High latency identification
  - Malformed packet detection
- **Interactive Visualizations**: 
  - Packet length vs. index scatter plots
  - Timeline-based anomaly visualization
  - Protocol distribution charts
  - TLS packet sequence analysis
- **Security Recommendations**: Context-aware security recommendations based on detected anomalies
- **Export Functionality**: Download anomaly reports in CSV format

## 📋 Prerequisites

### Required Dependencies

- Python 3.7+
- Wireshark/tshark (for packet capture analysis)

### Python Libraries

```bash
pip install streamlit pandas matplotlib scikit-learn pyshark nest-asyncio numpy
```

### System Requirements

**For full functionality, install Wireshark:**
- **Windows**: Download from [wireshark.org](https://www.wireshark.org/download.html)
- **Linux**: `sudo apt-get install tshark` or `sudo yum install wireshark`
- **macOS**: `brew install wireshark`

## 🚀 Installation

1. Clone the repository:
```bash
git clone https://github.com/Gurjas2112/Wireshark_PCAP_Anomaly_Detection.git
cd Wireshark_PCAP_Anomaly_Detection
```

2. Install required Python packages:
```bash
pip install streamlit pandas matplotlib scikit-learn pyshark nest-asyncio numpy
```

3. Ensure Wireshark/tshark is installed and accessible from your PATH

## 💻 Usage

### Running the Application

Start the Streamlit web application:

```bash
streamlit run Streamlit_wireshark_capture.py
```

The application will open in your default web browser at `http://localhost:8501`

### Analyzing PCAP Files

1. **Upload a PCAP file**: Click "Browse files" in the sidebar and select your `.pcap` or `.pcapng` file
2. **Or use test dataset**: Check the "Use test dataset" option to analyze sample data
3. **Configure settings**: Adjust the anomaly threshold (contamination) slider (default: 0.05)
4. **View results**: Navigate through the tabs:
   - **Analysis**: Overall anomaly detection results and visualizations
   - **TLS Deep Dive**: Detailed TLS traffic analysis
   - **Recommendations**: Security recommendations based on findings
5. **Download report**: Export detected anomalies as CSV from the sidebar

## 📁 Project Structure

```
Wireshark_PCAP_Anomaly_Detection/
│
├── Streamlit_wireshark_capture.py   # Main application file
├── README.md                         # Project documentation
├── LICENSE                           # License information
│
├── sample.pcapng                     # Sample PCAP file for testing
├── network_caputure.pcapng          # Network capture sample
├── dbus_system.pcapng               # D-Bus system capture sample
└── NMAP_PROBE.pcap                  # NMAP probe capture sample
```

## 🔧 Configuration

### Anomaly Detection Parameters

- **Contamination**: Controls the proportion of outliers in the dataset (range: 0.01 - 0.2)
  - Lower values: Detect fewer but more significant anomalies
  - Higher values: Detect more potential anomalies with higher sensitivity

### Packet Analysis Limits

- Default maximum packets analyzed: 1000 (for performance)
- Modify in code if needed for larger captures

## 🛡️ Anomaly Types Detected

| Anomaly Type | Description |
|-------------|-------------|
| **High Packet Length** | Packets exceeding 1500 bytes |
| **Low Packet Length** | Unusually short packets (<100 bytes) |
| **Retransmission** | TCP retransmissions indicating network issues |
| **Reset Flag** | TCP reset flags suggesting connection problems |
| **TLS Fragmentation** | Multiple sequential TLS packets indicating fragmentation |
| **Unusual HTTP Traffic** | Abnormal HTTP packet patterns |
| **High Latency** | Excessive time delays between packets |
| **Potential DoS Pattern** | High-frequency communication suggesting DoS attacks |
| **Malformed Packet** | Packets with missing or invalid information |
| **Unexpected Protocol** | Unknown or unusual protocols |

## 📊 Example Output

The tool provides:
- Summary statistics of detected anomalies
- Bar charts showing anomaly type distribution
- Top source/destination IP addresses in anomalies
- Communication pattern analysis
- Detailed packet-by-packet analysis with recommendations
- Timeline visualization of anomalous traffic
- Protocol distribution charts

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the terms specified in the LICENSE file.

## 🙏 Acknowledgments

- Built with [Streamlit](https://streamlit.io/)
- Uses [scikit-learn](https://scikit-learn.org/) for machine learning
- Powered by [PyShark](https://github.com/KimiNewt/pyshark) and Wireshark's tshark

## 📞 Support

For issues, questions, or contributions, please visit the [GitHub repository](https://github.com/Gurjas2112/Wireshark_PCAP_Anomaly_Detection).

## ⚠️ Disclaimer

This tool is for educational and security analysis purposes. Always ensure you have proper authorization before analyzing network traffic. Use responsibly and in compliance with applicable laws and regulations.
