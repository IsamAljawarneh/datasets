The data is a hyperlocal Air quality data collected using a mobile sensor Network, which is a low-cost air quality sensing network for cities and a research project
includes over 100 locations in Chicago, Illinois, USA.
This network was deployed starting in July, 2021

Each table includes the following columns.

- City, City where the Microsoft Eclipse device is deployed, Byte_array
- DeviceId: Id for a given device, Int32
- LocationName: Unique string describing the device location, Byte_array
- Latitude: Latitude of the device location, Double
- Longitude: Longitude of the device location, Double
- ReadingDateTimeUTC: The UTC date time string (like 2022-03-04 20:27:25.000) when the reading from the Eclipse sensor was recorded, Int96
- PM25: Uncalibrated Fine particulate matter (PM 2.5) in µg/m³, Double
- CalibratedPM25: Calibrated PM 2.5 in µg/m³, Double
- CalibratedO3: Calibrated Ozone in PPB, Double
- CalibratedNO2: Calibrated Nitrogen Dioxide in PPB, Double
- CO: Uncalibrated Carbon monoxide (CO) in PPM, Double
- Temperature: Degree Celsius, Double
- Humidity: Relative humidity, Double
- BatteryLevel: Device battery level in Volts, Double
- PercentBattery: Percent of device battery: Double
- CellSignal, Cellular signal strength in dB: Double