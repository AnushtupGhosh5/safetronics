# Topic 03: Sensor Datasheet Verification - COMPLETE

**Status:** ✅ Research Complete  
**Priority:** CRITICAL  
**Phase:** 1 - Foundational Research  
**Research Date:** 2025-10-20

---

## Executive Summary

**ALL 7 SENSORS VERIFIED AS ESP32-COMPATIBLE (3.3V logic)**

✅ **No I2C address conflicts detected**  
✅ **Total current draw: ~250mA (all sensors active)**  
✅ **All sensors support 3.3V operation**  
⚠️ **DHT22 uses single-wire protocol (not I2C)**  
⚠️ **MQ-7 requires 5V heater (separate power rail needed)**

---

## Verified Sensor Specifications

### 1. VL53L0X - ToF Distance Sensor

**Operating Voltage:** 2.6V - 5.5V ✅ (3.3V compatible)  
**Logic Level:** 3.3V ✅  
**I2C Address:** 0x29 (7-bit) / 0x52 (8-bit write)  
**Current Draw:** 10mA (idle), 40mA (ranging)  
**I2C Speed:** Up to 400 kHz (Fast Mode)  
**Pull-ups:** 4.7kΩ recommended  
**Price:** ₹56 (Robu.in) ✅ended)
recomm-CAM on (ESP32r-selectiocontrolledget-micrTopic:** bu  
**Next 25-10-2020pdated:** 
**Last U   HIGHnfidence:**CoMPLETE  
**COtatus:** ✅ arch Sese

**R
---20]
025-10-essed 2pdf [AccL53L0X_DS./9/a/6/V/assets/8/9comrkfun.ps://cdn.spaeet." htt3L0X Datash"VL5s. icronarkFun Elect5. Sp
15-10-20]
ssed 202/ [Accel0x/vl53sensorss.dev/espboardps://www. htt"or Pinout.ensnce Sistat D-Fligh Time-ofL0X2 VL53"ESP3SPBoards. 
14. E10-20]
 2025-ccessednsor/ [A-field-seneticule-magl-3-axis-mod5883273-hmcct/gy-bu.in/produ://rohttps." orens Stic Fieldule MagneMod83L 3 Axis Y-273 HMC58"G. Robu.in. 1310-20]

nced 2025-re." [Refesheetatar Dc Sensotiagnes ML 3-Axi83n. "QMC58poratio2. QST Cor
125-10-20]
sed 20le/ [Accesmodunsor-e-sessur-prearometrical-bbmp180-digitproduct/u.in/s://robttp." hsor Moduleure Sentric Pressgital Barome"BMP180 Di. 
11. Robu.in10-20]
renced 2025-et." [Refer DatasheSensossure Digital Pre0 P18"BMSensortec.  Bosch 0]

10. 2025-10-2Accessedr-module/ [so-sencoal-gasoxide-n-monco-carbooduct/mq-7-u.in/pr//rob" https:ule.ensor Mode Coal Gas SMonoxidO Carbon Q-7 C. "M9. Robu.in-10-20]

025d 2Reference" [tasheet.nsor Dae Gas Seid Monox"MQ-7 Carbonronics. Electanwei 
8. H-20]
2025-10d [Accessety-sensor/ iditure-hummperagital-te302-di22-am2/product/dht.in//robu" https:ty Sensor.re Humidiratutal TempegiM2302 Di "DHT22 Aobu.in.0]

7. R25-10-2nced 20reefe" [Rr Datasheet.nsomidity Seature and Huperl TemigitaT22 Dcs. "DHroni ElectAosong-20]

6.  2025-10r/ [Accessedeleromete-2-acc-gyro-sensor/mpu-6050ct.in/produ/robu https:/lerometer."nsor 2 Acce6050 Gyro SeU-"MPn. 

5. Robu.i025-10-20] 2ferencedRedf [atasheet1.pPU-6000-Dation." MSpecific Product 5060U-6000/MPU-"MPnse/TDK. Se Inven-20]

4.025-10essed 2or/ [Acce-sensstancdilaser-based-lidar-53l0x-tof-n/product/vlps://robu.i" httce Sensor.taner DisLIDAR LasOF Based L0X T"VL53n. 
3. Robu.i20]
5-10-ed 202cessf [Acbreakout.pdensor-ce-sistanar-d-lidx-micro-vl53l0dafruitads/pdf/aownloruit.com/darn.adafleps://cdn-kout." httBreae Sensor AR Distanccro LID"VL53L0X MiAdafruit. 

2. ]-10-20essed 2025 [Accx.pdf3l0/vl5atasheet/en/desourcest.com/rwww. https:// sensor."ranginglight Time-of-Ftasheet - L0X Danics. "VL53roMicroelect

1. STsonitati

## Co

---petition demore comr MQ-7 befheat** fohour pre48-an  **Pl10)
5. ⚠️ups (₹ for pull-**torsΩ resisOrder 4.7k ✅ **ule
4.camera modf separate  instead o**SP32-CAM**Use E MQ-7
3. ✅ or) fM (₹50-100 to BOverter**oost con-b5V buck️ **Add 2. ⚠e
compatiblified  verase** - allsor purchith senroceed w

1. ✅ **Pt Steps Nex
---

##easible
te rate f 10Hz updable** -chievaring atime monitoReal-
8. ✅ **lem) probin (not arate GPIO p uses sepat I2C** - **DHT22 nos
7. ⚠️all sensoror  - ₹665 fet**udghin bll witst we
6. ✅ **Core SDA/SCLrs shanso4 seient** - ics suff I2C bu **Single5. ✅power
r use USB t oboos - add buck-5V rail**MQ-7 needs  **k)
4. ⚠️ea(~250mA pable** agedraw manwer **Total po
3. ✅ on same busl al use - canonflicts** 2C address c**No Iogic)
2. ✅ le** (3.3V l-compatibESP32sensors . ✅ **All 

1Key Findings---

## 

 budget)(84% of35 :** ₹3,5, powerrsto moing for MCU,**Remaint |

hin budge| ✅ Wit*  **₹665***TOTAL** ||  |
cal10 | Loors (3×) | sist-up ren |
| Pull129 | Robu.i883L | QMC5
| |u.in 33 | Rob BMP180 | 
|.in | Robu |-7 | 119 |
| MQ | Robu.inDHT22 | 139|
| | Robu.in 050 | 179 PU-6|
| Mn bu.i| 56 | RoL53L0X | V-----|
------|-------- |
|------|) | Source| Price (₹
| Item ary
t Summ-

## Cos).

-- ₹400-500d solution,* (integrate instead*dule mo2-CAMUse ESP3**project.  budget mplex for* - Too co*OV7670*ded
7. *Not Recommenc.

### ❌ ematiproblf 5V is ves iatialterny) as ualitair q35** (or **MQ-1r price)  similai-gas,* (multider **MQ-2* Consr preheat.48-houl and ai 5V ruires** - ReqQ-7al
6. **Mprovl Ap️ Conditionasor

### ⚠senmp/humidity liable te** - Re5. **DHT22ion backup
orientatompass/ cood for3L** - G**QMC588sure
4. ude/pres altit, good for-low power* - Ultra. **BMP180*king
3tion tracor orientacellent f Ex0** - **MPU-605ment
2. measurell distancect for waPerfe53L0X** - . **VLo Issues)
1Sensors (Nroved 
### ✅ Appns
mmendatio

## Reco-```

--mA)
ter (150l → MQ-7 Hea└── 5V Raige divider
ith voltaoutput) wg -7 analo ADC (MQpull-up
├──with 4.7kΩ ata pin) IO (DHT22 d── GP3L (0x0D)
├── QMC5880x77)
│   └ (─ BMP180  ├─x68)
│ 50 (0─ MPU-60├─   x29)
│(0VL53L0X ──    ├ups
│ 4.7kΩ pull- SCL) with2C Bus (SDA,ic)
├── I3.3V Log-CAM (``
ESP32

`implified)m (Sgra Wiring Dia--

##ors

-most sens0Hz for vable at 1* ✅ Achieg:*torin-time monial
**Re100ms |
-50 Hz | 5-00 Hz | 1083L | 2MC58|
| Q-25.5ms 10 Hz | 4.528 Hz | 1-80 | 1e |
| BMP1espons 150s rous | 1 Hz |-7 | Continums |
| MQz | 2000 | 0.5 H0.5 Hz
| DHT22 | z | 1ms |0 Hz | 100 HU-6050 | 100
| MP0-30ms | Hz | 2| 10-20z L0X | 50 H-|
| VL53---|------------------|----------------|--|
|Latency ed | ndecomme R Max Rate |nsor |
| Setes
n RauisitiocqData A
## --
tal)

-0 to7kΩ (₹5-1 3× 4. needed:**resistorstal n)

**Ton data pi (ol-up to 3.3V10kΩ pul* 4.7kΩ - 2:*)

**DHT2tire busfor enpair e V (onto 3.3 pull-ups :** 4.7kΩ, SCL)us (SDA

**I2C Bents Requiremesistor Pull-up R-

##ng.

--ng testiUSB 5V duriuse ttery, or from bail e 5V ranerat geonverter to cbuck-boost** Use Q-7:on for M*Solution |

*onnecti cDirect✅ Yes | .3V | 6V | 3.16-3. 2| QMC5883L |ion |
ect connectYes | Dir | 3.3V | ✅ 0 | 1.8-3.6V |
| BMP18ge dividerl + voltaeds 5V raitial | Neal) | ⚠️ PargnV (si 3.3 | (heater)7 | 5Von |
| MQ-ti connecect| Dir Yes 3.3V | ✅V |  | 3.3-6T22
| DHt I/O || 5V toleran| ✅ Yes 3V/5V -3.46V | 3. 2.375| MPU-6050 |tion |
necon| Direct c3V | ✅ Yes  3.2.6-5.5V | | 
| VL53L0X-----|-----------|------------|-|----------------------|---
|--otes |atible? | Nomp Cic Level |tage | Logol Vputnsor | In3V

| SeLevel:** 3. Logic 

**ESP32ityilatibmpLevel Co Voltage 

##e

---cal runtimetiheor tursmAh) = 10 ho-ion (25008650 Ligin)
- 1h safety maritntime w ruurs12 ho(8--3000mAh ded: 2000
- RecommenAh minimum50mr = 2hou- 250mA × 1 
30-60min:**or t fequiremenery R

**Batttive)P32-CAM acensors + ES250mA (all snt Draw:** ~re**Peak Cur

r only |tehea MQ-7 **150** |** |  | **150OTAL (5V)**|
| **Tter out MQ-7 hea06** | With**2 | **94** | (3.3V)**AL OT**Tactive |
| era | With cam0 | 160 2-CAM | 8 |
| ESP3At 200Hz5 | 0.35 | 0783L | 0.C58er |
| QMlow pow12 | Ultra- | 0.0180 | 0.005il) |
| BMPter (5V ra50 | Hea7 | 150 | 1| MQ-ls |
 interva| 2-sec | 1.5 22 | 0.05HTous |
| Dinu | Cont3.9 | 3.90 | -605
| MPUging mode |0 | 40 | Ran 1| VL53L0X |------|
---------|---|------|--------------tes |
|-A) | Notive (mAce (mA) | | Idl

| Sensor Analysisdget er Bu

## Pow

---FLICTS** CONRESS NO I2C ADD

**✅| ❌ No | No 0 | 0x21 | ❌
| OV767| N/A |) | ❌ No ogN/A (analMQ-7 | /A |
| | ❌ No | NA (not I2C) T22 | N/ed) |
| DH| ❌ No (fix0D | ❌ No 3L | 0xMC588|
| QNo (fixed)  ❌  | ❌ No |180 | 0x77|
| BMP(AD0 pin) es ❌ No | ✅ Y69 | 0x68 or 0xPU-6050 |  |
| Mrogrammable)es (p| ❌ No | ✅ YL0X | 0x29 
| VL53---------|-----------|-|-------------------------|-
|------able? |ct? | Changeflion | Cess (7-bit)dr2C Ad| Sensor | I
ress Map
AddI2C 

## 

--- issues.ompatibilityliminating cESP32, eera + egrated camas intwhich h(₹400-500) tead * inse*AM modulse **ESP32-C:** Udationommen
**Rec pins
cant GPIOd signifiers an level shiftres - RequiEXPL ⚠️ COMity:**bilti

**Compad)  mate (esti:** ₹200-300rice 
**PA (640x480) VGsolution:** )  
**Re0mA (activew:** 6 Dra
**Current(read)  e) / 0x42  (writ* 0x21ess:*I2C Addrial  
**rallel/serke) + pa(I2C-li** SCCB **Interface: ⚠️  
, 1.8V (I/O)3V (core)ge:** 3.ng Voltatiera)

**Oppecsed in sMention670 (OV7e - era Modul 7. Cam
---

### ESP32
for ✅ PERFECT ity:**atibil
**Compest
lf-tuilt-in se BHz, 200Hz
-0Hz, 10010Hz, 5data rate: 
- Output 1mGaussn: esolutioµT)
- RGauss (200Range: ±2 
- ensingfield setic  3-axis magn
-tures:** Fea 

**KeyRobu.in) ✅ ** ₹129 (  
**Price:mmendedkΩ reco:** 4.7-ups**Pull  
00 kHz** Up to 4C Speed:Hz)  
**I2200), 350µA (** 75µA (1Hznt Draw:**Curreixed)  
x0D (fAddress:** 0I2C  ✅  
*** 3.3Vic Level:*e)  
**Logpatiblcom3V  (3. 3.6V ✅ -16V** 2.tage:ing Vol**Operat
ometer
Axis MagnetC5883L - 3-### 6. QM--

r ESP32

-CT fo✅ PERFEtibility:** 
**Compapower
ltra-low ded
- Uor inclunserature se
- Tempitude)m alt1 hPa (±8acy: ±- Accur00m
 to +90tion: -500me calcula
- AltitudhPa 300-1100 re range:
- Pressu*Features:*
**Key .in) ✅  
(Robu33  ₹****Price:d  
ecommendekΩ r.7** 4**Pull-ups:  
 Mode)SpeedMHz (High to 3.4 ed:** Up  
**I2C Speample/sec) µA (1 sdby), 12** 5µA (stannt Draw:**Curre  
ixed)x77 (fss:** 0dre**I2C Ad✅  
3.3V evel:** 
**Logic Lble)  ompati✅ (3.3V cV V - 3.6e:** 1.8 Voltagratingor

**Opeure Sensetric PressP180 - Barom

### 5. BM

---in.t pigital outpuer OR use dltage dividx) with vo3.3V maDC (gh ESP32 Aouhrt tnalog outpur, read afor heateail arate 5V r:** Use sep
**Solution output
digitalOR use og reading r for analideoltage div + verV for heat REQUIRES 5:** ⚠️tibility
**Compaomparator)
ith c (wavailablel output  Digitaut: 0-5V
-ge outplog voltads
- Anasecontime: <150 nse spo- Reimum)
in hours (mal), 24(optim hours  48heat time:
- Prepm CO000 pcts: 20-2ete Des:**
-eatur*Key F 

*bu.in) ✅ ** ₹119 (RoPrice:**3Ω  
e:** 31Ω ±  ResistancHeater
**(signal)   <1mA ter),* 150mA (hearent Draw:*ured)  
**C(ADC requiralog output * Ane:*erfac 
**Inttput) ✅ nalog oumpatible (aV co3.3 Level:** 
**Logices 5V)  ir requater 5V ⚠️ (heltage:**rating VoOpe**nsor

 SeMonoxide Gasbon 7 - Car MQ-
### 4.---

 I2C)
, notses GPIOmpatible (u2 coESP3lity:** ✅ **Compatibismission

it data tran
- 40-bn requiredle GPIO ping Si
-racy)2-5% accu% RH (±ity: 0-100cy)
- Humid.5°C accura (±0 to 80°C0°Cerature: -4mp*
- Te:*atures Fe**Key

 obu.in) ✅ * ₹139 (R 
**Price:*d 10kΩ requirekΩ - * 4.7p:*-u**Pull)  
onds every 2 sec.5 Hz (once* 0:*ling Rate  
**Sampstandby)A (0µsuring), 51.5mA (meat Draw:** 1-
**Curren ⚠️  OT I2C)tal (Ne-wire digi:** Singlocolrot  
**P.3V ✅ Level:** 3ic*Logatible)  
*3V compV ✅ (3.- 6V  3.3e:**agng Volterati*Op

*dity Sensormiture & Huempera T DHT22 -# 3.

##

--- for ESP32 ✅ PERFECTibility:**ated

**Compncludnsor ire seatuer- Tempssor)
Procen tiol MoigitaDMP (D Built-in 
-DCit A- 16-b
0 °/s00 ±2±500, ±1000,: ±250, is gyroscope- 3-axg
g, ±8g, ±16ter: ±2g, ±4omeis acceler**
- 3-ax Features:

**Keyu.in) ✅  79 (Rob:** ₹1ice**Prmmended  
-10kΩ recoernal 2.2kΩle, extal availabern IntPull-ups:** 
**to 400 kHz :** Up  Speed2C*I  
*rs active)l senso** 3.9mA (alw:t Dra
**Currenhigh)  0x69 (AD0 ) or ltau68 (def0xress:**  
**I2C Add ✅ olerant3V or 5V tLevel:** 3.*Logic le)  
*.3V compatib 3.46V ✅ (35V -tage:** 2.37ng Volperatiyro)

**Oter + GcceleromeMU (A I50 - 6-Axis# 2. MPU-60
---

##
CT for ESP32* ✅ PERFEity:***Compatibilonflict)

hange if c canC address (ce I2ammablrogrlass 1)
- P (eye-safe CerEL las40nm VCS- 9 ±3% at 2m
 Accuracy:mm
-00m - 20- Range: 30m:**
eatures
**Key F  
