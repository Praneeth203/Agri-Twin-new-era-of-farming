Agri Twin 🚜🌾
Team Mithuna's Autonomous Crop Scanning Unit

Revolutionize your fields! 🌿 This is a futuristic agricultural bot designed to make farming smarter, not harder. It offers precision field scanning for 1-acre plots, real-time disease detection using the power of Jetson Orin Nano 🧠, and live health visualization via the Agro Twin App 📱. Say goodbye to crop loss and hello to maximum yield! 🚀

🚜💨 Agri Twin: The Smart Farming Assistant 🤖🔎
Welcome to the future of Agriculture! This project is designed to act as a "Digital Twin" for your farm. It combines remote-controlled mobility, Edge AI computer vision, and instant data visualization to detect diseases in Tomato, Chili, and Corn crops before they spread.

✨ Key Features
📍 Precision Field Scanning: Designed specifically to navigate and map standard 1-acre field segments, ensuring no plant is left unchecked.

🦠 Real-Time Disease Detection: Uses the Jetson Orin Nano and Pi Camera v2 to identify pests and diseases on the fly—no internet needed for processing!

📱 Live Visualization App: A dedicated "Agro Twin" mobile app that displays the bot's findings, highlighting "danger zones" in the field.

⚡ Edge Computing Power: All heavy AI processing happens right on the bot, ensuring zero latency even in remote farms with poor connectivity.

🛡️ Multi-Crop Support: Specialized models trained to detect specific ailments in Tomato, Chili, and Corn.

🛠️ Technology Stack
🤖 Hardware: NVIDIA Jetson Orin Nano Developer Kit, Raspberry Pi Camera Module v2, Motor Driver (L298N/L293D), DC Motors, Custom Chassis.

🧠 AI & Backend: Python, PyTorch/TensorFlow, TensorRT (for optimization), OpenCV.

🎨 Frontend/App: Mobile App Framework (Flutter/React Native), WebSocket.

📡 Communication: Wi-Fi/Bluetooth (Local Telemetry), HTTP.

⚙️ System Architecture & Workflow
Here’s how the magic happens from the soil to your screen!

🚜 On-Field Patrol:

The bot enters the field.

The Pi Camera v2 acts as the eyes 👁️, capturing high-res video streams of the plant leaves.

🧠 Edge Processing (The Brain):

The Jetson Orin Nano receives the video feed via the CSI port.

It runs a custom-trained YOLO-based model (optimized with TensorRT) to spot diseases like Early Blight or Leaf Curl.

📡 Data Transmission:

If a disease is found, the bot tags the location and the disease type.

This packet of information is beamed instantly to the user's phone. 📲

🖥️ User Interface:

The Agro Twin App updates the field map.

Farmers get a visual alert: "Alert! 🚨 Tomato Blight detected in Sector 4."

🔌 Hardware & Pin Diagram
This setup is centered around the powerful Jetson Orin Nano.

Component,Connection to Jetson,Purpose
Pi Camera v2 📷,CSI Connector,Captures high-res plant images for AI analysis
Motor Driver ⚙️,GPIO Header (PWM pins),Controls the movement/speed of the bot
Wi-Fi Module 📡,M.2 Key E (Integrated),Communicates data to the Agro Twin App
Battery 🔋,DC Jack / 5V Pins,Powers the AI beast!

Friendly Reminder! 💡 The Jetson Orin Nano is sensitive to power fluctuations. Ensure you are using a stable 19V power supply or a regulated battery pack to prevent sudden shutdowns during AI inference!

Plaintext

       +-----------------------+
       |   Jetson Orin Nano    |
       |                       |
       |      [CSI Port]-------|-----> 📷 Pi Camera v2
       |                       |
       |      [GPIO Pins]------|-----> ⚙️ Motor Driver -----> 🚜 Wheels
       |                       |
       |      [Wi-Fi]----------|-----> 📱 Agro Twin App
       |                       |
       +----------|------------+
                  |
                 🔋 Power Supply
🚀 Core Functionalities Explained
🧠 Edge AI Disease Recognition
This isn't just a remote-control car; it's a pathologist on wheels!

Training: We used a dataset (via Roboflow) containing thousands of images of healthy vs. diseased leaves for Tomato, Chili, and Corn.

Inference: The model runs locally on the Orin Nano. By using TensorRT engines, we achieve high FPS (Frames Per Second), meaning the bot doesn't need to stop to think—it scans while it moves.

🎮 Remote Navigation & Scanning
The Problem: Manual inspection of a 1-acre field takes hours and is prone to human error.

The Solution: The user controls the bot to sweep the field. As it moves, the field of view covers the crop rows. The video feed is analyzed in real-time, effectively "scanning" the field 10x faster than a human could.

📱 "Agro Twin" App Visualization
Data is useless if you can't read it.

Live Feed: View exactly what the bot sees through the camera.

Health Map: The app generates a visual representation of the scanned area. Green dots = Healthy; Red dots = Disease Detected. This allows for "Spot Treatment"—spraying only where needed, saving money on pesticides! 💰

📈 Analytics and Future Scope
This project is just the beginning of autonomous farming! 🌱

🤖 Fully Autonomous Navigation: Upgrade to ROS 2 (Robot Operating System) for Lidar-based path planning so the bot drives itself without a human controller.

💦 Automated Spraying Mechanism: Attach a nozzle and tank. When the AI detects a disease, the bot automatically sprays that specific plant.

☀️ Solar Integration: Add solar panels for extended runtime in the fields.

📊 Long-term Health Tracking: Save data over the season to predict disease outbreaks before they happen based on weather patterns.

Developed with ❤️ by Team Mithuna
