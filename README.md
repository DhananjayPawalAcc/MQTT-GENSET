# MQTT-GENSET
Data Collection and Thingsboard demo by which we can replicate data subscribed by subscriber on thingsboard.


Real-Time Genset Monitoring System
This project enables real-time monitoring of genset data using an MQTT-based pipeline integrated with ThingsBoard, a popular IoT platform. The system supports local monitoring and global sharing using ngrok, making it accessible from any device without additional setup.

Workflow
Publisher Side (Raspberry Pi):
The Raspberry Pi gathers genset data.
It publishes the data to an MQTT broker using main_publisher.py.
Subscriber Side (Laptop):
The laptop subscribes to the MQTT broker via main_subscriber.py.
The data is sent to ThingsBoard for visualization.
ThingsBoard Visualization:
Local Access: Monitor data via http://localhost:8080/home.
Global Access: Use ngrok to expose ThingsBoard to the internet and share a public URL.
Step-by-Step Guide
1. Set Up the Raspberry Pi
a. SSH into the Raspberry Pi
ssh accurate@192.168.1.45
b. Connect to a Wi-Fi Network or Mobile Hotspot
sudo nmcli dev wifi rescan
nmcli dev wifi list
sudo nmcli dev wifi connect "DeviceName" password "    "
Note: Password is 4 spaces.
c. Exit the SSH Session
exit
d. Reconnect via SSH to the New IP Address
ssh accurate@<new_ip_address>
e. Navigate to the Publisher Directory
cd Desktop/pigenset
f. Run the Publisher
python3 main_publisher.py
2. Set Up the Subscriber
a. Run the Subscriber Script on Your Laptop
python3 main_subscriber.py
3. Visualize Data on ThingsBoard
a. Open ThingsBoard Locally
Open your browser and go to:
http://localhost:8080/home
Log in with the following credentials:
Username: dhananjay.p@accurateic.in
Password: accurate
b. Use ngrok for Global Access
Install ngrok and authenticate with your token. Refer to ngrok setup instructions.
Run the following command:
ngrok http 8080
Share the public URL (e.g., https://<random-string>.ngrok-free.app) with your client.
Your client can open the URL in their browser to access the ThingsBoard dashboard.
