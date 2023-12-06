Home-Energy-Monitoring-System
=============================

Just a simple energy monitoring system using :-

1. Raspberry pi
2. Eastron SDM 230 energy meter
3. Modbus RS 485 to USB converter to read my house energy consumptions through Modbus RS 485 protocol

## About & How It Works 

Just a simple project which I used as my Final Year Project during my degree :)

![FYP Method](https://github.com/Anmirazik/Home-Energy-Monitoring/assets/113960675/da63a4a8-6cc1-47e9-bf46-8ee3ae3f6bf9)


1. Read the Modbus raw data based on the Eastron SDM 230 documentations manual , you can just get it online or download it from this repo
2. Decode the Modbus raw data into readable format or more specifically decode it into float data type
3. Build a JSON object for ease of reading so your eyes wont hurt :)
4. Publish the JSON object to InfluxDB as well as MQTT Broker for easy access of the Data and persistent storage for further analysis
5. Build Grafana dashboard for data visualizations

### Step 1: Data Generations (Modbus RS 485)

Below JSON object is the example data output which the Node-Red program has processed

~~~
{
   "Voltage":233.97,
   "Instantaneous Current":10.97,
   "Instantaneous Power":2549.95,
   "Frequency":50.05,
   "Energy Consumptions":19541.08,
   "Instantaneous Apparent":2553,
   "Instantaneous Reactive":124.68,
   "Power Factor":0.999,
   "Maximum Power Demand":10291.84,
   "Maximum Current Demand":47.44
}

~~~

### Step 2: Data Transmission (MQTT Mosquitto Broker)

Below image shows the JSON object has been successfully published to the MQTT Broker , I viewed all the topics in the broker using MQTT Explorer

![image](https://github.com/Anmirazik/Home-Energy-Monitoring/assets/113960675/00914dce-dacc-4586-ab1e-b6392af3481b)


### Step 3: Data Storage (InfluxDB)

Below image shows the JSON object has been succesfully inserted into the databasse (InfluxDB)

![image](https://github.com/Anmirazik/Home-Energy-Monitoring/assets/113960675/d87f1936-465d-4931-82ec-af3ebf8a76ec)


### Step 4: Data Visualizations (Grafana)

Below Image shows my final dashboard using Grafana for Monitoring Home Energy Consumptions

<img width="954" alt="image" src="https://github.com/Anmirazik/Home-Energy-Monitoring/assets/113960675/3797ed19-bd04-449d-9783-704bffa98e21">


