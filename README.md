🎯 LeverUp C2 Framework

LeverUp is an advanced, web-based Command & Control (C2) framework for security research. It provides a modern web interface to manage remote agents (bots), execute system commands, perform file transfers, and simulate post-exploitation tasks in a controlled lab environment.

✨ Core Features

    🌐 Web Control Panel: An intuitive dashboard to manage all connected bots and send commands.

    🤖 Bot Management: View real-time status, system info (OS, architecture, admin privileges), and manage multiple bots simultaneously.

    💻 Remote Command Execution: Execute system commands on selected bots and view the output.

    🖱️ Interactive Shell Mode: Switch to an interactive shell for any bot for direct command input.

    📁 File Transfer: Upload and download files to/from remote bots.

    📊 Live Event Logging: Real-time logging of all bot activities, commands, and system events with filtering capabilities.

    🧩 Modular Payloads: Includes a set of C++ bot payloads demonstrating various capabilities, including lateral movement and persistence.

    ⚡ Real-time Communication: Powered by WebSockets (Flask-SocketIO) for seamless, low-latency communication between the server and connected bots.


🛠️ Tech Stack

Backend	Python, 
(Flask, 
Flask-SocketIO)

Frontend	HTML5, CSS3, JavaScript 

Real-time	WebSockets (Flask-SocketIO, python-socketio)

Bot Payloads	C++ (Windows API)


🚀 Getting Started

These instructions will guide you through setting up the C2 server on your machine.

📋 Prerequisites

    Python 3.7+ and pip

    Git (to clone the repository)

    Basic knowledge of networking (IP addresses and ports)


⚙️ Installation

Clone the repository:
    
    bash
    git clone https://github.com/Yashaswi-kankarla/leverup.git
    cd leverup

Install the required Python packages:
    The project dependencies are managed in requirements.txt.

    bash
    pip install -r requirements.txt

This installs Flask, Flask-SocketIO, and other necessary libraries.


🖥️ Running the C2 Server

Configure the Server (Optional):
    You can modify the server's IP and port directly in the app.py file. By default, it runs on 0.0.0.0:8080.

Start the server:

    bash
    python app.py

 Access the Web Panel:
    Open your web browser and navigate to http://127.0.0.1:8080. You should see the LeverUp control panel.


🤖 Deploying a Bot (Payload)

The payload/ directory contains various C++ bot implementations.

Configure the Bot:
    In the payload source code (e.g., lever-up.cpp), you must change the C2_SERVER_IP and C2_SERVER_PORT to match your server's IP and port.
    cpp

    // Update these lines in the bot's source code
    std::string C2_SERVER_IP = "YOUR_SERVER_IP";
    int C2_SERVER_PORT = 8080;

Compile the Bot (on Windows):
    You need a C++ compiler, like MSVC (Visual Studio). Compile the .cpp file into an executable.
    bash

    # Example compilation command using the Visual Studio Developer Command Prompt
    cl /EHsc lever-up.cpp ws2_32.lib user32.lib advapi32.lib shell32.lib
    

Run the Bot:
    Execute the generated .exe file on the target Windows machine. The bot will attempt to connect to your C2 server.


📖 Usage Guide

Once the server is running and a bot is connected, you'll see it appear in the left panel of the web interface.
        Selecting Bots: Click on a bot's card to select it. Use the "All" or "None" buttons to manage multiple selections.
        Sending Commands: Type a command (e.g., whoami, ipconfig, dir C:\) into the "Command Center" text box and click "Send". The output will appear in the logs.
        Shell Mode: For an interactive shell, select a bot and click "Shell Mode - Enable". You can then type and send commands one after another.
        Event Logs: All events are shown in the "Event Logs" section. You can filter logs by type (Success, Error, Warning, etc.).                                
    LeverUp is designed to be straightforward and user-friendly. Simply run the app.py script to launch the web control panel, then access the interface through your browser. From the main dashboard, you can select connected bots, send system commands, transfer files, and monitor real-time logs – all through an intuitive point-and-click interface.


⚠️ Important Legal & Ethical Disclaimer

  This tool is intended for educational and research purposes only.
  Unauthorized use on systems you do not own or have explicit permission to test is illegal and unethical. The developer assumes no liability for any             misuse or damage caused by this software.
  This tool should only be used for ethical and legal penetration testing activities. Unauthorized use is strictly prohibited.

🤝 Contributing

Your contributions to improve LeverUp are welcome! Feel free to submit a Pull Request or open an Issue for bugs or feature suggestions.
Feel free to star, fork, or contribute to this project! Your support and contributions are greatly appreciated.

📄 License

This project is currently unlicensed, meaning all rights are reserved. You may view and fork the code, but you are not permitted to use, modify, or distribute it without explicit permission from the author.


📫 Contact & Support

  For questions, suggestions, or feedback, please reach out to Yashaswi Kankarla.

    GitHub: @Yashaswi-kankarla

    LinkedIn: https://www.linkedin.com/in/kankarla-yashaswi/

    Email: yashaswikankarla@gmail.com

    Project Link: https://github.com/Yashaswi-kankarla/leverup
