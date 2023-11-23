Home-Energy-Monitoring-System
=============================

Just a simple energy monitoring system using Raspberry pi , Eastron SDM 230 energy meter, Modbus RS 485 to USB converter to read my house energy consumptions through Modbus RS 485 protocol

### About

Just a simple project which I used as my Final Year Project during my degree :)

### How It Works 

1. Read the Modbus raw data based on the Eastron SDM 230 documentations manual , you can just get it online or download it from this repo
2. Decode the Modbus raw data into readable format or more specifically decode it into float data type
3. Build a JSON object for ease of reading so your eyes wont hurt :)
4. Publish the JSON object to InfluxDB as well as MQTT Broker for easy access of the Data and persistent storage for further analysis
5. Build Grafana dashboard for data visualizations
