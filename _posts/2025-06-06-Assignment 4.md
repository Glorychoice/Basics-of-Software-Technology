# Assignment 4 Report

# Project Title: GNSS Satellite Geometry Evaluator for BeiDou B3I
 - Student: Ameh Glory Ene-dugbo-ojo
 - Student ID: LS2425231
 - University: Beihang University (Hangzhou Regional Center)
 - Program: M.Sc. Space Technology Applications
 - Date: June 10th 2025
 
#  1. Introduction and Objective
- This software project aims to evaluate GNSS (Global Navigation Satellite System) signal performance using
 real-world BeiDou B3I data collected from a mobile receiver. The system provides tools to analyze signal
 quality, satellite visibility, and positioning geometry, which are critical for understanding and improving
 GNSS-based applications in adverse environments.
 The core functionalities include: - Conversion of raw NMEA and proprietary BeiDou logs to structured CSV 
Visualization of satellite SNR (Signal-to-Noise Ratio) - Calculation and plotting of DOP (Dilution of Precision)
 values - Skyplot and time-series analysis of satellite data - Interactive GUI for user control and result viewing


#  2. Background and Relevance
- GNSS performance can be significantly impacted by satellite geometry, signal strength, and environmental
 conditions. This is especially relevant for applications in agriculture, autonomous navigation, and urban
 environments where multipath and weak signals are common. BeiDou B3I signals offer strong performance
 in Asia-Pacific, making them ideal for testing. However, tools for visualizing and analyzing these logs are
 often unavailable or expensive. This project provides an open, Python-based, GUI-assisted evaluator
 developed using AI assistance


# 3. Technical Challenges
- Parsing mixed-format BeiDou logs containing BDGGA, BDGSV, BDDHV, and RAWSTAT messages
 Extracting usable information such as PRN, SNR, elevation, azimuth
 Estimating DOP from satellite distribution without direct position fix data
 Creating accurate plots (skyplot, time-series, etc.) from limited fields
 Integrating all functionalities into a responsive and user-friendly GU

# 4. Development Environment
 - Operating System: Windows 11 Home 64-bit
 Processor: Intel(R) Core(TM) i7 CPU
 RAM: 16 GB
 Python Version: 3.10 (Anaconda)
 Environment: Glory (conda virtual environment)
 Libraries Used: pandas, matplotlib, numpy, tkinter
 AI Model Used: ChatGPT (OpenAI GPT-4.5/o4

# 5. Development Process
**Step 1: Data Collection**       
        -Real-world BeiDou data was collected using a receiver saved in .log format.
        -File path: **E:\with internet-middle - DATA.log** 

**Step 2: Data Conversion**
        -Developed convert_**log_to_csv.py** to extract BDGSV, BDGGA messages.
        -Output: **b3i_sample_data.csv**
        
**Step 3: Analysis Module**
        -Created **b3i_evaluator.py** to compute:
        -Number of satellites
        -Average SNR
        -Min/Max elevation
        -HDOP estimate
        -Plots: SNR vs. Elevation, Skyplot
        
**Step 4: GUI Development**
       -Built **b3i_gui_evaluator.py** with tkinter:
       -Load CSV button
       -Plot display buttons
       -Console feedback
       
**Step 5: AI Integration**
      -ChatGPT assisted in all phases:
      -Python scripting
      -GUI debugging
      -Data parsing
      -Plotting logic
      -File handling

# Results
      - CSV Summary: SNR values across PRNs, estimated DOP, satellite count
      - Skyplot: Polar plot showing satellite distribution
      - SNR Plot: Elevation vs. SNR line plots
      - Time-series View: SNR over timestamp (optional enhancement)
      - GUI: Buttons for loading data, generating plots, and saving outputs
      
- The results of the project demonstrate that the GNSS tool effectively parsed and analyzed BeiDou B3I data, generating clear visualizations such as skyplots, SNR graphs, and DOP curves. The satellite geometry analysis revealed how the Dilution of Precision (DOP) values varied over time, highlighting the impact of satellite distribution on positional accuracy. Overall, the tool provided valuable insights, confirming that selecting satellites with higher SNR and optimal geometry leads to more accurate and reliable GNSS positioning results.

# 7. Source Code Access
  - **Project files include:** 
  - **convert_log_to_csv.py**
  - **b3i_real_data.log**
  - **b3i_evaluator.py**
  - **b3i_sample_data.csv**
  - **b3i_gui_evaluator.py**
  - **outputs/**

import csv

# Input and output files
log_file = "b3i_real_data.log"
csv_file = "b3i_sample_data.csv"

# List to hold extracted data
data = []

with open(log_file, 'r') as file:
    for line in file:
        if line.startswith("$BDGSV"):
            parts = line.strip().split(',')

            # Each BDGSV line holds info for up to 4 satellites
            total_fields = len(parts)
            for i in range(4, total_fields - 4, 4):
                try:
                    prn = parts[i]
                    elevation = float(parts[i + 1])
                    azimuth = float(parts[i + 2])
                    snr = float(parts[i + 3])
                    data.append([prn, elevation, azimuth, snr])
                except (ValueError, IndexError):
                    continue  # Skip malformed entries

# Write to CSV
with open(csv_file, 'w', newline='') as out:
    writer = csv.writer(out)
    writer.writerow(['PRN', 'Elevation', 'Azimuth', 'SNR'])  # Header
    writer.writerows(data)

print(f"✅ Converted {len(data)} satellite entries to {csv_file}")

# C:\Users\hp\Documents\b3i_gnss_evaluator\outputs\summary_stats.csv,PRN,Elevation,Azimuth,SNR
- count,20739.0,20739.0,20739.0,20739.0
- mean,182.58151309127732,49.90915666136265,197.21587347509524,40.23303920150441
- std,19.219181527127507,16.72571333323216,84.89948176960478,3.4080422147958136
- min,161.0,25.0,52.0,29.0
- 25%,167.0,39.0,141.0,38.0
- 50%,179.0,45.0,201.0,40.0
- 75%,198.0,67.0,238.0,43.0
- max,220.0,82.0,353.0,46.0

# C:\Users\hp\Documents\b3i_gnss_evaluator\outputs\summary.txtTotal Satellites: 20739
- Average SNR: 40.23
- Max Elevation: 82.0
- Min Elevation: 25.0

# PRN,Elevation,Azimuth,SNR
- 161,45.0,137.0,39.0
- 162,35.0,232.0,36.0
- 163,52.0,198.0,40.0
- 167,82.0,353.0,43.0
- 170,69.0,321.0,40.0
- 173,39.0,208.0,39.0.....

# ![image](https://github.com/user-attachments/assets/f9e4d5cf-c03b-49f7-80fa-b0f3641ca31f)
# ![image](https://github.com/user-attachments/assets/5a8eef66-3ec9-47fb-994c-790292300b1a)


# Summary
- For Assignment 4, I developed a GNSS Satellite Geometry Optimizer using real BeiDou B3I data collected from field testing. The main goal was to improve position accuracy by analyzing satellite visibility, SNR quality, and calculating DOP values (GDOP, PDOP, HDOP, VDOP). A custom Python tool was implemented to convert the raw .log file into structured .csv, visualize satellite geometry through skyplots, and plot SNR and trajectory data. Additionally, I integrated a simple GUI using Tkinter to make the tool user-friendly. An optional AI-assisted module was tested to label satellite quality based on signal strength and geometry. This project highlights how GNSS signal analysis, satellite selection, and real-time visualization can work together to optimize navigation accuracy in challenging environments.

#  8. Conclusion
 The project successfully demonstrates how BeiDou B3I GNSS data can be parsed, visualized, and evaluated
 using an AI-assisted software development process. It provides a user-friendly tool for satellite geometry
 analysis and can be extended to include multi-constellation support and real-time monitoring. The use of
 large language models significantly accelerated development and debugging.

 # 9. Future Work
  - Add real-time serial port reading
  - Add KML export for trajectory
  - Integrate AI models for anomaly detection in GNSS signals
  - Extend to multi-GNSS: GPS, Galileo, GLONASS
    
# References
- BeiDou Navigation Satellite System ICD
- GNSS-SDR 
- NGS DOP
- Skyplot Design Reference – georinex & matplotlib
- Pandas, NumPy, Matplotlib Official
- Pyproj & Geopandas 
- Python Tkinter GUI 










