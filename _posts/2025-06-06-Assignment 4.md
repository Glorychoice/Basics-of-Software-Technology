# Project Topic: GNSS Satellite Geometry Optimizer for Enhanced Position Accuracy in Challenging Environments

# Project Objectives:
- Analyze real-world BeiDou B3I GNSS data.
- Optimize satellite selection based on DOP (Dilution of Precision).
- Provide visualizations: SNR plots, skyplot, trajectory, and satellite visibility.
- log-to-CSV conversion, basic AI-assistance, and GUI.

- Real-world GNSS data  log file: E:\with internet-middle - DATA.log
- GNSS Data Source: BeiDou B3I data

- Functional Modules:
- Log file parser (.log → .csv)
- DOP calculator
- Skyplot generator
- SNR visualizer
- Optional AI-assisted module for satellite classification
- GUI using Tkinter or PyQt

# Tools and Environment
- Operating System: Windows 11 (with WSL Ubuntu)
- Programming Language: Python 3.12

# Libraries Used:
- pandas, matplotlib, numpy – data processing and plotting
- pyproj, geopandas – coordinate and map handling
- tkinter – GUI
  
# Resuls
- 

- For Assignment 4, I developed a GNSS Satellite Geometry Optimizer using real BeiDou B3I data collected from field testing. The main goal was to improve position accuracy by analyzing satellite visibility, SNR quality, and calculating DOP values (GDOP, PDOP, HDOP, VDOP). A custom Python tool was implemented to convert the raw .log file into structured .csv, visualize satellite geometry through skyplots, and plot SNR and trajectory data. Additionally, I integrated a simple GUI using Tkinter to make the tool user-friendly. An optional AI-assisted module was tested to label satellite quality based on signal strength and geometry. This project highlights how GNSS signal analysis, satellite selection, and real-time visualization can work together to optimize navigation accuracy in challenging environments.

# Conclusion
This project demonstrates how GNSS performance can be improved by carefully analyzing satellite geometry and signal quality. It bridges raw BeiDou B3I data with visual and algorithmic tools for better decision-making. Through the integration of Unix-style processing, Python-based visualization, and optional AI assistance, the developed software provides an extensible framework for GNSS research and optimization tasks.

# References
- BeiDou Navigation Satellite System ICD
- GNSS-SDR 
- NGS DOP
- Skyplot Design Reference – georinex & matplotlib
- Pandas, NumPy, Matplotlib Official
- Pyproj & Geopandas 
- Python Tkinter GUI 










