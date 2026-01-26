# High Frequency High Power Amplifier based on CGHV40030


## Design Outlines & Component List

<div align="center">

| Component | Model | Notes |
|----------|-------|-------|
| RF power device | Wolfspeed / Cree / MACOM CGHV40030 | |
| RF board | Rogers RO4003C | |
| SMD resistors | Ideal | Package size: 0603 |
| SMD ceramic capacitors for matching networks | Murata GQM Series High-Frequency HiQ | 0.1 – 200 pF, package size: 0603 |
| SMD ceramic capacitors for bias lines decoupling | Murata GRM Series High-Frequency HiQ | 0.1 – 100 µF, package size ≥ 0603 |

</div>

<div align="center">

| Requirements | Values |
|-------------|--------|
| VDS | 50 V |
| IDSq | 150 mA |
| Bandwidth | 2.9 – 3.1 GHz (200 MHz) |
| Small Signal Gain | > 15 dB |
| Input Return Loss | > 7 dB |
| Saturated POUT | 43.5 dBm (@ 4 dB gain compression) |
| Drain Efficiency | > 55% (@ 4 dB gain compression) |
| Gain Compression | < 4 dB |

</div>


## Bias

To bias the device at a drain current of **150 mA**, a gate voltage (**VGSQ**) of **−2.54 V** is required.

The simulation test bench and the obtained results are shown below.
<div align="center">
  <img src="https://github.com/user-attachments/assets/4827b2a8-e034-4dc1-b950-2b8f008295c7" width="600" />
</div>
<div align="center">
  <img src="https://github.com/user-attachments/assets/81a4c61d-af3e-4c55-a62a-7ed162b7cc11" alt="Image" width="600" />
</div>



## Stability Analysis

To ensure **unconditional stability** over the widest possible frequency range without sacrificing gain, an **RC stabilization network** was added at the gate, with:

- **R = 50 Ω**
- **C = 5.8 pF**

This network guarantees unconditional stability in the **0–20 GHz** frequency range, satisfying the following conditions:

- **μ > 1**
- **μ′ > 1**
- **Rollet stability factor K > 1**

<div align="center">
  <img src="https://github.com/user-attachments/assets/0a8c411c-8645-4dde-824e-915270e3eea6" alt="Image" width="600" />
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/5ab99f34-24b3-49f9-946a-6e3bcf7978c2" alt="Image" width="600" />
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/dd0c3bbe-c20b-4608-b697-a2a148bd0070" alt="Image" width="600" />
</div>


## Load Pull Analysis

A **load-pull instrument** was used to determine the load that maximizes power transfer.

The following values were obtained:

- **Source impedance**:  
  Z<sub>S</sub> = Z<sub>in</sub><sup>*</sup> = **1.007 − j4.703 Ω**

- **Load impedance**:  
  Z<sub>L</sub> = Z<sub>out</sub><sup>*</sup> = **7.671 + j10.143 Ω**

<div align="center">
  <img src="https://github.com/user-attachments/assets/b4832da6-4298-4c94-95af-03da77e80b90" alt="Image" width="600" />
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/04356515-c43e-462b-9923-6f3f7bdcfb77" alt="Image" width="600" />
</div>


## Input Matching Network

<div align="center">
  <img src="https://github.com/user-attachments/assets/536ae00e-c331-4c16-8d06-2c5ca693e3bb" alt="Image" width="600" />
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/797b58a0-ecef-42f6-97fe-438e7824549c" alt="Image" width="600" />
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/b0bd8759-98c8-47e8-9799-8d90d3a32996" alt="Image" width="600" />
</div>

## Output Matching Network

<div align="center">
  <img src="https://github.com/user-attachments/assets/b437cc5e-4fe8-4052-83ee-f5a3e4a277b6" alt="Image" width="600" />
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/813af0d2-aca1-4edc-b56a-a521842067a3" alt="Image" width="600" />
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/fcc2316e-993e-4d80-8715-ae30eb99d5b0" alt="Image" width="600" />
</div>


## Final Circuit and Performance Evaluation

In the final circuit, **two decoupling capacitors** with a value of **C_dec = 2.2 µF** were added.

Instead of ideal DC feed inductors, a **transmission line with appropriate dimensions** was used to prevent AC signals from entering the bias network. This solution was combined with **proper decoupling capacitors** to ensure stable biasing and RF isolation.

<div align="center">
  <img src="https://github.com/user-attachments/assets/422d384b-5631-43d9-b474-46d1cd28720c" alt="Image" width="600" />
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/f9ea7311-b49f-49d3-be11-7ad8168e46eb" alt="Image" width="600" />
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/8e95fd55-bf2a-4bc5-846a-963891db7b7a" alt="Image" width="600" />
</div>


## Two-Tone Analysis

For the intermodulation test, two tones were selected at **2.995 GHz** and **3.005 GHz** (10 MHz spacing) to perform a **Harmonic Balance analysis**.

<div align="center">
  <img src="https://github.com/user-attachments/assets/38faa066-e7d7-4744-a54f-643373d871c0" alt="Image" width="600" />
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/e124fc82-3632-4c5b-b29e-81fd91906d47" alt="Image" width="600" />
</div>


## Final Specifications and Performance

<div align="center">

| Specifications        | Requested                     | Reached        |
|-----------------------|-------------------------------|----------------|
| Small Signal Gain     | > 15 dB                       | > 19 dB       |
| Input Return Loss     | > 7 dB                        | > 7 dB        |
| Psat                  | > 43.5 dBm                    | > 46 dBm      |
| Drain Efficiency      | > 55% (@ 4 dB gain compression) | > 70%        |

| Parameter             | Condition                     | Measured      |
|-----------------------|-------------------------------|---------------|
| IIP3                  | @ P_avs = -10 dBm             | 29 dB         |
| OIP3                  | @ P_avs = -10 dBm             | 47 dB         |

</div>

