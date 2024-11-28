# MQTT-GENSET
Data Collection and Thingsboard demo by which we can replicate data subscribed by subscriber on thingsboard.


<h2>Real-Time Genset Monitoring System</h2>

<p>This project provides real-time monitoring of genset data using an <strong>MQTT-based pipeline</strong> and <strong>ThingsBoard</strong> for visualization. The data can be accessed locally or globally through <strong>ngrok</strong>, allowing easy sharing without additional setup on the client side.</p>

<h3>Workflow Overview</h3>
<ol>
  <li><strong>Publisher Side (Raspberry Pi):</strong> Gathers genset data and publishes it to an MQTT broker using <code>main_publisher.py</code>.</li>
  <li><strong>Subscriber Side (Laptop/Server):</strong> Subscribes to the MQTT broker via <code>main_subscriber.py</code> and sends the data to ThingsBoard for visualization.</li>
  <li><strong>ThingsBoard Visualization:</strong> Access data locally at <code>http://localhost:8080/home</code> or globally using ngrok's public URL.</li>
</ol>

<h3>Step-by-Step Guide</h3>

<h4>1. Raspberry Pi Setup (Publisher)</h4>

<b>SSH into the Raspberry Pi:</b>
```bash
ssh accurate@192.168.1.45

<b>Connect to a Wi-Fi Network or Mobile Hotspot:</b>

```bash
sudo nmcli dev wifi rescan
nmcli dev wifi list
sudo nmcli dev wifi connect "DeviceName" password "    "
```

<p><em>Note: Password is 4 spaces.</em></p>
<b>Exit the SSH Session:</b>

```bash exit
```

<b>Reconnect to the Raspberry Pi with the New IP Address:</b>

```bash
ssh accurate@<new_ip_address>
```

<b>Navigate to the Publisher Directory:</b>

```bash
cd Desktop/pigenset
```
<b>Run the Publisher:</b>

```bash
python3 main_publisher.py
```

<h4>2. Laptop/Server Setup (Subscriber)</h4>
<b>Run the Subscriber Script:</b>
<ul> <li>Go to: <code>http://localhost:8080/home</code></li> <li>Log in with the following credentials:</li> <ul> <li><strong>Username:</strong> dhananjay.p@accurateic.in</li> <li><strong>Password:</strong> accurate</li> </ul> </ul>
<b>Use ngrok for Global Access:</b>

```bash
ngrok http 8080
```

<p>Share the public URL provided by ngrok (e.g., <code>https://<random-string>.ngrok-free.app</code>) with others.</p>

