# arys-automotive-protection

## Automotive Reverse Polarity & Load Dump Protection Circuit

This project presents the LTspice simulation and analysis of an automotive-grade ECU input protection circuit designed for:

- Reverse battery protection
- Load dump transient suppression
- Input surge protection

## Main Components

- F1: 10A Automotive Fuse
- D1: P6KE33A TVS Diode
- M1: IRF7404 P-Channel MOSFET
- R1: 10kΩ Gate Pull-down Resistor
- C1: 100µF Output Capacitor
- R2: 100Ω ECU Load Model

## Simulation Tests

1. Normal 12V Operation
2. Reverse Battery Protection (-12V)
3. 100V Automotive Load Dump

## Software Used

- LTspice XVII
- GitHub
- Microsoft Word

## Repository Structure

- /schematics → LTspice schematic files
- /simulations → RAW simulation outputs
- /waveforms → waveform screenshots
- /report → final PDF report

## Author

Ananya Devraj
Arys Garage Technical Assignment — Q4