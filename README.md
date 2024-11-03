# Cuffless Blood Pressure Monitoring System

This repository contains the implementation of a non-invasive, cuffless blood pressure monitoring system that uses pulse transit time (PTT) measurements between two PPG sensors placed on the chest to estimate blood pressure.

## Overview

The system uses two TCRT5000L infrared sensors placed 5cm apart on the chest to detect blood pulses. The time delay between these pulses (PTT) is used to estimate blood pressure through a calibrated relationship.

## Requirements

- Python 3.8+
- Jupyter Notebook
- Libraries: numpy, pandas, matplotlib, scipy
- OWON VDS1022I Oscilloscope (for real-time data acquisition)

## Installation

```bash
git clone https://github.com/23875658/cuffless-bp-monitoring.git
cd cuffless-bp-monitoring
pip install -r requirements.txt
```

## Usage

### Running the Jupyter Notebook
```bash
jupyter notebook vds1022i.ipynb
```

### With CSV Files
Load and run the notebook cells with the CSV file path configured for your data files.

### With OWON VDS1022I
To use with the oscilloscope:
1. Install the OWON VDS1022I drivers and API following instructions at [OWON-VDS1022 API](https://github.com/florentbr/OWON-VDS1022)
2. Uncomment and run the device setup cells in the notebook
3. Connect your oscilloscope via USB

## CSV File Naming Convention for accessing calibration data
The CSV files follow this naming format:
`output_with_time{systolic}_{diastolic}_{heartrate}.csv`

Example: `output_with_time125_77_79.csv` represents:
- Systolic: 125 mmHg
- Diastolic: 77 mmHg
- Heart Rate: 79 BPM

## Results

The system achieves:
- Average deviation of 5.86% for systolic pressure
- Average deviation of 8.11% for diastolic pressure
- Heart rate measurements within 3.02% average deviation
- Effective range: BP below 165/85 mmHg and HR below 95 BPM

## Acknowledgments

This project was completed as part of Project (E) 448_2024 at Stellenbosch University under the supervision of Dr W. Smit.
