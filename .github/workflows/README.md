# GoodEarth Malhar Weather Data Archive

This repository serves as a centralized, high-accuracy hourly log for weather data at **GoodEarth Malhar, Bengaluru**. 

##  How it Works
The data is collected from an **Ambient Weather WS-2902** station (MAC: `BC:FF:4D:81:A7:64`). 

Unlike standard snapshots, this repository uses a **60-minute historical averaging method**:
1. Every hour, a GitHub Action fetches the last 60 data points from the station.
2. It filters out sensor noise (ignoring invalid zeros for temperature and humidity).
3. It calculates a mathematical average to represent the hour accurately.
4. Data is stored in IST (Asia/Kolkata).

## Data Structure
Files are organized by date for easy access:
`data/device/hourly/YYYY-MM-DD/HH-00.json`

### Key Data Points:
- **Outdoor:** Temperature (°C), Humidity (%), Feels Like, and Dew Point.
- **Wind:** Hourly Average Speed (km/h) and Maximum Hourly Gust (km/h).
- **Rain:** Hourly, Daily, and Weekly cumulative totals (mm).
- **Solar:** UV Index and Solar Radiation (W/m²).
- **Indoor:** Temperature and Humidity for the station's base unit.


---
*Maintained by the GoodEarth Weather Bot.*
