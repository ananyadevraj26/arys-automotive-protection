## Automotive Reverse Polarity & Load Dump Protection Circuit

This project presents the LTspice simulation and analysis of an automotive-grade ECU input protection circuit designed for:

- Reverse battery protection
- Load dump transient suppression
- Input surge protection

## Main Components

- Fuse: 10A Automotive Fuse
- D1: P6KE33A TVS Diode
- M1: IRF7404 P-Channel MOSFET
- R1: 10kΩ Gate Pull-down Resistor
- C1: 100µF Output Capacitor
- R2: 100Ω ECU Load Model

## Simulation Tests

1. Normal 12V Operation
2. Reverse Battery Protection (-12V)
3. 100V Automotive Load Dump

## Tools Used

- LTspice XVII
- GitHub
- Microsoft Word

## Repository Structure
arys-automotive-protection/ │ ├── README.md ├── schematics/ ├── simulations/ ├── waveforms/ └── report/

## How to Run the Simulation

1. Install LTspice XVII  
   https://www.analog.com/ltspice

2. Clone this repository:

```bash
git clone https://github.com/ananyadevraj26/arys-automotive-protection.git
```

3. Open LTspice  
   File → Open →  
   `schematics/automotive_protection_circuit.asc`

4. Run the transient simulation:

```spice
.tran 10m
```

5. Probe the following signals:

- VIN
- VOUT
- I(D1)
- Id(M1)

## Test Configurations

| Test | V1 Configuration |
|------|------------------|
| Normal 12V Operation | `DC = 12, Rser = 2` |
| Reverse Polarity | `DC = -12, Rser = 2` |
| Load Dump Surge | `PULSE(12 100 2m 1u 100u 500u 10m), Rser = 2` |

## Simulation Results

| Test | Fault Condition | Simulation Result | Overall Status |
|------|------------------|------------------|----------------|
| **Test 1** | Normal 12V Operation | `VOUT ≈ 11.76V` steady, nominal load current drawn | **PASS** |
| **Test 2** | Reverse Polarity (-12V) | `VOUT = 0V`; complete downstream isolation achieved | **PASS** |
| **Test 3** | 100V Load Dump Surge | TVS clamps transient successfully; full self-recovery by 4ms | **PASS** *(with limitation)* |


## Author

Ananya Devraj
