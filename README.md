Call Detail Record (CDR) Inter-Operator Settlement System
A C++ Client–Server Socket Programming Project
Overview
This project implements a TCP-based Client–Server application in C++ for processing Call Detail Records (CDRs) used in Inter-Operator Settlement (IOS).
The Server stores CDR files and provides them when requested.
The Client requests the CDR file, downloads it, and processes:
• Incoming & outgoing voice calls
• Incoming (MT) & outgoing (MO) SMS records
• GPRS data usage (download & upload MB)
Processed data is stored using STL containers, and subscriber identity is based on MSISDN (max 7 digits).
⸻
Project Structure
Project/
│
├── bin/                    # Compiled executables (client, server)
├── inc/                    # Header files
│   ├── processing.h
│   └── sock.h
│
├── obj/                    # Object files
│   ├── login.o
│   ├── mainClient.o
│   ├── mainServer.o
│   ├── processing.o
│   └── sock.o
│
├── src/                    # Source code
│   ├── login.cpp
│   ├── mainClient.cpp
│   ├── mainServer.cpp
│   ├── processing.cpp
│   └── sock.cpp
│
├── Make/                   # Build system
│   └── Makefile
│
├── data.cdr                # Sample Call Detail Records
├── OperatorFile.txt        # Operator metadata/config (if required)
└── ReadmeProject.txt       # Original internal README

Technologies Used
• C++ (C++11 or higher)
• TCP/IP Socket Programming
• STL Containers
• Makefile build system
⸻
Building the Project
Just run:
make
This will compile all object files into the obj/ directory and generate executables inside the bin/ directory.
Expected output:
bin/client
bin/server
The client will:
1. Connect to the server
2. Request the data.cdr file
3. Receive and store the file
4. Process all CDR records
5. Store parsed output in STL containers (calls, SMS, GPRS)
6. CDR Data Format
data.cdr contains raw telecommunication records such as:
• Outgoing voice calls
• Incoming voice calls
• Outgoing SMS (MO)
• Incoming SMS (MT)
• GPRS data usage (upload/download)
Each line contains subscriber MSISDN and usage details.
⸻
Unit Testing
If you include Unit Testing.zip in the repo:
• Extract the testing folder
• Build tests using make test (if test Makefile is provided)
• Validate individual modules (processing, socket layer, etc.)
⸻
Features Summary
• Full TCP client–server communication
• Requests and retrieves CDR file over sockets
• Parses CDR data into structured STL containers
• Handles voice, SMS, and GPRS records
• Modular design: header files in inc/, logic in src/
• Easy compilation via Makefile
⸻
Author
Shristi
(Created as a demonstration of advanced C++ socket programming and telecom CDR processing)  
