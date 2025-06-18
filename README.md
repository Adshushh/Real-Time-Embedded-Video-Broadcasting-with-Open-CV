 📡 PiCam LiveStream with OpenCV and Python

A real-time video streaming system built using a Raspberry Pi and Pi Camera, designed to stream live footage to a browser or local device. The project uses Python, OpenCV, and PiCamera2 for video handling. All development was performed remotely from a laptop using SSH over a dynamic IP network.

---

🧰 Components Used

- Raspberry Pi 3 (any model with camera support)
- Pi Camera (v2 or HQ camera)
- Raspberry Pi OS (Bookworm recommended)
- Python 3
- PiCamera2 library
- OpenCV
- Flask (for hosting the video stream and web frameworks)
- SSH (for remote development via laptop)
- Local network (Wi-Fi or Ethernet)

---

⚙️ General setup and explainations 
 - Let me walk you throught the whole process and how the connectivity is established 
   1. Raspberry Pi is a mini-computer, it needs power, IO devices, CPU, GPU etc. Raspberry Pi uses a ARM based CPU for core processes.
   2. It has 2 usb2 and 2 usb3 and 1 ethernet port. And one usb-b port for power in earlier models.
   3. Plug it into a power source, add a wifi dongle if the pi is an earlier model.
   4. Connect a display and start the configuration by installing raspberry pi os which is open source,
   5. Connect to a wifi via a module or an ethernet port. Most wifi's have a DHCP, DHCP is a network protocol used to automatically assign IP addresses to devices on a network.
   6. When you connect to the wifi, an IP address is assinged to the Raspberry Pi. Now the rapberry pi is ready to connect via ssh ( secure shell ). SSH is how you can remotely access the raspberry pi in your laptop. This will come handy when a monitor or any IO device is not available.
   7. If the raspi terminal is comfortable you may code in that itself avoiding ssh connectivity.
   8. Now to connect via ssh, first get the IP. To get the IP run this command in the raspberry pi's bash : hostname -I, this will fetch the IP
   9. Now switchover to your laptop or any other device and open bash and type in : ssh pi@<the-IP-you-got-in-the-revious-step>.
   10. Then enter the password, the password is "raspberry" which comes as default within the pi module.
   11. Now the connection via SSH is made and now you can access files / run commands on the raspberry pi modula via your laptop.
       
---

🔌 Hardware Setup

1. Connect the Pi Camera to the Raspberry Pi's camera slot. (Pull up the slot and put in the cable for the pi-cam, make sure the blue side faces the ethernet ports)
2. Open your terminal , SSH or GUI.
3. Enable the camera using: sudo raspi-config - Interface options - camera - select enable , then press esc consecutively to exit the tab.

---

🛠️ Install Dependencies

Update your Pi and install all required packages, I have included the linux commands in the linux basics section 

---

🧠 Project Code Overview

The Python script:

- Captures video using PiCamera2
- Uses OpenCV for image processing
- Streams frames using Flask over HTTP
- The code is available in the repo file ( pythonconfig )
- Make a python file in raspberry pi and copy paste the code in the repo, then run it. the video service will now be hosted
- You can understand the web hosting and the back-end logic if you look into the code once.

---

🧪 Future Improvements

Add motion detection with OpenCV
Enable password protection on the stream
Deploy over the internet via port forwarding or ngrok

---

📸 Final Notes

This project demonstrates how to deploy a lightweight livestream solution using Raspberry Pi, with full Linux-based remote control and camera integration. Ideal for home surveillance, robotics, or embedded CV systems.
