# Topic 03: Sensor Datasheet Verification

**Status:** ✅ COMPLETE  
**Priority:** CRITICAL  
**Date:** 2025-10-20

## Executive Summary

✅ ALL 7 SENSORS ESP32-COMPATIBLE  
✅ No I2C conflicts  
✅ Total: ~250mA  
⚠️ MQ-7 needs 5V rail

## Verified Specifications

### 1. VL53L0X - ToF Distance
- Voltage: 2.6-5.5V ✅
- I2C: 0x29 (programmable)
- Current: 10-40mA
- Price: ₹56 ✅

### 2. MPU-6050 - IMU
- Voltage: 2.375-3.46V ✅
- I2C: 0x68/0x69
- Current: 3.9mA
- Price: ₹179 ✅

### 3. DHT22 - Temp/Humidity
- Voltage: 3.3-6V ✅
- Protocol: Single-wire (not I2C)
- Current: 1-1.5mA
- Price: ₹139 ✅

### 4. MQ-7 - CO Gas
- Voltage: 5V heater ⚠️
- Interface: Analog
- Current: 150mA
- Price: ₹119 ✅
- **Needs 5V rail**

### 5. BMP180 - Pressure
- Voltage: 1.8-3.6V ✅
- I2C: 0x77
- Current: 5-12µA
- Price: ₹33 ✅

### 6. QMC5883L - Magnetometer
- Voltage: 2.16-3.6V ✅
- I2C: 0x0D
- Current: 75-350µA
- Price: ₹129 ✅

### 7. Camera - Use ESP32-CAM
- Integrated solution ✅
- Price: ₹400-500
- Eliminates OV7670 complexity

## I2C Address Map

| Sensor | Address | Conflict |
|--------|---------|----------|
| VL53L0X | 0x29 | ❌ No |
| MPU-6050 | 0x68 | ❌ No |
| BMP180 | 0x77 | ❌ No |
| QMC5883L | 0x0D | ❌ No |

✅ NO CONFLICTS

## Power Budget

- 3.3V rail: 206mA peak
- 5V rail: 150mA (MQ-7 only)
- Total: ~250mA
- Battery: 2500mAh = 10hr runtime

## Cost

Total sensors: ₹665  
Remaining: ₹3,535 (84%)

## Recommendations

✅ All sensors approved  
✅ Use ESP32-CAM (not OV7670)  
⚠️ Add 5V buck-boost (₹50-100)  
✅ 4.7kΩ pull-ups needed (₹10)

## Citations

1. STMicroelectronics VL53L0X Datasheet
2. Adafruit VL53L0X Guide
3. Robu.in product pages (all sensors)
4. InvenSense MPU-6050 Datasheet
5. Aosong DHT22 Datasheet
6. Hanwei MQ-7 Datasheet
7. Bosch BMP180 Datasheet
8. QST QMC5883L Datasheet
9. ESPBoards VL53L0X Guide
10. SparkFun VL53L0X Datasheet

**Confidence:** HIGH  
**Next:** budget-microcontroller-selection
