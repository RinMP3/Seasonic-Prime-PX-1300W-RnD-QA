# Seasonic Prime PX-1300W RnD & QA

| Parameter | Specification / Metadata |
| :--- | :--- |
| **Test Subject** | Seasonic PRIME PX-1300 (1300W, 80 PLUS Platinum / SSR-1300PD) |
| **Category** | R&D / QA Hardware Validation |
| **Author / Engineer** | RinMP3 |
| **Equipment Used** | UNI-T UT320D Thermometer, Precision True RMS DMM |
| **Date** | August 12, 2026 |

### Executive Summary & Key Validation Metrics

| Metric | Physical DMM / Measured | Target / Offset | Operational State |
| :--- | :---: | :---: | :---: |
| **+12V Rail** | `12.160 V` | +1.33% Nominal Offset (`+0.53%` vs OCCT) | Optimal Margin |
| **+5V Rail** | `5.060 V` | +1.20% Nominal Offset (`+2.02%` vs OCCT) | Optimal Margin |
| **Thermal Delta ($\Delta T$)** | `2.2 °C` | $T_1\text{ (Exhaust)} - T_2\text{ (Ambient)}$ | Low Thermal Load |
| **Acoustic Profile** | `0 dB` (Passive) | Hybrid Mode ON (`~270W` Load) | `0 RPM` Passive Operation |

 **Audit Objectives & Scope:** Comprehensive physical and telemetry evaluation of Seasonic PRIME PX-1300.  
 **Core Objective:** Cross-validate physical voltage potentials (Hardware DMM) against motherboard telemetry (OCCT/Super I/O), analyze thermal behavior under Hybrid fan control, and evaluate packaging/cable ergonomics.

### Test Rig & Methodology

* **CPU:** AMD Ryzen 7 5800X (Overclocked, PPT 124W)
* **GPU:** NVIDIA GeForce RTX 5060 (TDP 146W)
* **Total System Load:** `~270W` Continuous (`~20.8%` Nominal Load)
* **Instrumentation:** UNI-T UT320D Thermometer, True RMS DMM, OCCT v12+

### Electrical Validation: Hardware DMM vs. Software OCCT

| Power Rail | OCCT Software Reading | DMM Hardware Measurement | Absolute Delta (V) | Deviation (%) | R&D Assessment |
| :--- | :--- | :--- | :---: | :---: | :---: |
| **+12V Line** | `12.096 V` (Avg: `12.132 V`) | **`12.160 V`** | `+0.064 V` | `+0.53%` | `Optimal / Pass` |
| **+5V Line** | `4.960 V` (Avg: `4.981 V`) | **`5.060 V`** | `+0.100 V` | `+2.02%` | `Optimal / Pass` |
| **+3.3V Line** | `3.328 V` (Max: `3.344 V`) | **`3.330 V`** (est.) | `+0.002 V` | `+0.06%` | `Optimal / Pass` |

 **Key Engineering Insight (Super I/O Sensor Offset):** Physical DMM probing verified **12.160V (+12V)** and **5.060V (+5V)**. Telemetry readings were lower than the corresponding DMM measurements by 0.064–0.100 V. This discrepancy may be attributable to differences in measurement points, Super I/O / ADC calibration, PCB trace resistance, and/or contact resistance. The measured +12 V output of 12.160 V provided additional voltage margin relative to the 12.000 V nominal target under the tested ~270 W overclocked system load. This measurement does not by itself characterize transient response.

### Thermal & Acoustic Profile

* **T1 Exhaust / T2 Ambient / $\Delta T$:** `30.3 °C` / `28.1 °C` / **`2.2 °C`**
* **Hybrid Mode ON (270W):** No PSU fan noise observed in Hybrid Mode (`0 RPM` passive mode).
* **Hybrid Mode OFF:** Forced FDB fan activation maintains ambient temperatures.

### Usability, Ergonomics & Cable UX Analysis

* **Unboxing & Accessories:** Tool-free extraction, pre-built replacement manual, physical jumper starter tool included.
* **Cabling UX:** Highly flexible sleeved cables, native 12V-2x6 cable, and a rare 2x SATA cable ideal for minimalist builds.
* **Recommendation for Seasonic R&D:** Replace current tear-open plastic cable bags with reusable Ziplock bags for improved long-term UX.

### Final R&D / QA Engineer Verdict

The **Seasonic PRIME PX-1300 (SSR-1300PD)** platform exhibits benchmark electrical stability, exceptional voltage regulation, and an optimal thermal-acoustic profile. Physical DMM measurements confirm stable DC output voltages under the tested ~270 W overclocked system load. Fully recommended for high-load test rigs, extreme overclocking setups, and professional hardware evaluation labs.

<details>
  <summary><b> Photo Gallery</b></summary>
  <br>
<img width="2270" height="2270" alt="photo_1_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/ae5f6f5e-cc90-4913-bf71-2b26d9ad4a2e" />
<img width="2259" height="1694" alt="photo_4_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/1f0542a9-a951-4985-931f-1abbf404a840" />
<img width="2560" height="1920" alt="photo_5_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/97cab5c5-3d46-4f61-be4a-8f80b0d0f23c" />
<img width="2171" height="1628" alt="photo_6_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/83d1dfb7-9322-44a6-8580-1d727f0db139" />
<img width="2346" height="1759" alt="photo_7_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/dc547502-394c-4ebb-9318-43e7c96a0697" />
<img width="2189" height="1642" alt="photo_8_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/1a29b057-ef2f-40e2-8213-c9a36375cb37" />
<img width="2052" height="1539" alt="photo_9_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/253b3438-cadd-4142-b73c-34adf2e3948a" />
<img width="2189" height="1642" alt="photo_10_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/b16e0642-fe3c-4a5b-989b-2d2c50b501b7" />
<img width="2189" height="1642" alt="photo_11_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/724e159f-2d30-4263-ad75-1eaaecea1f03" />
<img width="2521" height="1891" alt="photo_12_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/b23db463-0443-465d-bbf6-5b1edef9efac" />
<img width="2237" height="1678" alt="photo_13_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/bdeb512d-583e-4e0f-b6cd-4720ba3fa72d" />
<img width="2237" height="1678" alt="photo_14_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/8290e422-9698-4976-8a8b-9f0f30b79d19" />
<img width="2237" height="1678" alt="photo_15_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/74b6c7b7-42d8-4bff-bba3-4604ced6e1f7" />
<img width="2237" height="1678" alt="photo_16_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/74e6998f-72a3-43ac-9eba-2de4b1fd46ff" />
<img width="2237" height="1678" alt="photo_17_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/fe25f9a3-20ef-4ff1-b9e2-c028dd4caedd" />
<img width="2434" height="1826" alt="photo_18_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/5001453a-7006-44ca-a849-54d941ac9ef5" />
<img width="2560" height="1920" alt="photo_19_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/eb9cf62e-e400-4255-ae85-0950d9f1a443" />
<img width="2560" height="1920" alt="photo_20_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/441773fa-e87b-4e8d-b94d-35998a51d58e" />
<img width="2231" height="1673" alt="photo_21_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/3de99b67-a676-49c8-bfc9-1d789e6a8eed" />
<img width="2560" height="1919" alt="photo_22_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/26ce0f1b-cfbd-4ae7-95c5-408da82ab0dc" />
<img width="2560" height="1919" alt="photo_23_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/c327f56b-4127-4eed-959e-27eaab839ebf" />
<img width="1358" height="1019" alt="photo_24_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/a6b14af9-b708-4014-abdc-175159285297" />
<img width="2560" height="1919" alt="photo_25_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/0289b70c-a626-4827-b1a4-fa8c09ee3eed" />
<img width="2560" height="1919" alt="photo_26_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/ba2a56d4-c3bb-4fa4-9f14-5094f7775ca8" />
<img width="2019" height="1514" alt="photo_27_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/61fb99ab-0156-424d-bf09-4cb8c87d4bb2" />
<img width="2019" height="1514" alt="photo_28_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/34cb7992-89a3-4896-b19c-0cdc21dadef1" />
<img width="2560" height="1920" alt="photo_29_2026-08-23_18-39-07" src="https://github.com/user-attachments/assets/61084627-a24d-455f-a043-8b8a4e9b2b24" />
</details>

<details>
  <summary><b> Thermal Logs</b></summary>
  <br>
<img width="4032" height="3024" alt="Hybrid_ON_OCCT" src="https://github.com/user-attachments/assets/e65e572f-8f4c-4c8d-8bf4-c9cc8bbf1a17" />
<img width="4032" height="3024" alt="Hybrid_ON_Thermometer" src="https://github.com/user-attachments/assets/a05b25d9-641e-49c8-a599-cf29fdec9e7b" />
</details>

<details>
  <summary><b> DMM & OCCT Logs</b></summary>
  <br>
  <img width="696" height="355" alt="OCCT_Voltage" src="https://github.com/user-attachments/assets/6370151b-6aa9-4302-bdb1-dfc0780c6685" />
  <img width="4032" height="3024" alt="Molex_4_Pin" src="https://github.com/user-attachments/assets/752589c3-21d9-41d6-938b-7e11de8d230a" />
  <img width="4032" height="3024" alt="5V" src="https://github.com/user-attachments/assets/f1865820-3274-4972-971f-6e873b418ef3" />
  <img width="4032" height="3024" alt="12V" src="https://github.com/user-attachments/assets/e8028d96-1bf5-40a1-845b-0c5f68118e0b" />
</details>


