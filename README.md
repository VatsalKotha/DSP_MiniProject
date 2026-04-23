# DSP Mini Project: Audio Signal Processing & Analysis

## Overview
This project is a Digital Signal Processing (DSP) application that performs audio signal analysis, visualization, and processing. It specifically focuses on analyzing target speech signals in the presence of masking/noise signals, with techniques for signal scaling and noise management.

## Project Structure
```
.
├── app.py                 # Main application script
├── signal_1.wav          # Target speech signal (clean speech)
├── signal_2.wav          # Masking signal 1 (background noise/interference)
├── signal_3.wav          # Masking signal 2 (background noise/interference)
├── signal_4.wav          # Masking signal 3 (background noise/interference)
└── README.md            # This file
```

## Features

### 1. **Time-Domain Signal Visualization**
   - Plots raw audio waveforms of 4 input signals
   - Shows the original speech and masking signals before processing
   - Displays amplitude vs. time for each signal

### 2. **Signal Masking & Scaling**
   - Implements a masker scaling function that:
     - Equalizes the lengths of target and masking signals
     - Scales masking signals to specified input SNR (Signal-to-Noise Ratio)
     - Uses standard deviation-based scaling

### 3. **Audio Signal Processing**
   - Reads WAV audio files using SciPy
   - Performs time-domain analysis
   - Computes time arrays for signal visualization
   - Supports multiple simultaneous signals

## Dependencies

- **numpy** (via pylab): Numerical computing
- **scipy**: Scientific computing and signal processing
- **matplotlib** (via pylab): Data visualization
- **pygame**: Audio/multimedia support (optional)

## Installation

### Prerequisites
- Python 3.x
- pip package manager

### Setup
```bash
# Install required dependencies
pip install numpy scipy matplotlib pygame

# Or create a virtual environment
python -m venv venv
source venv/bin/activate  # On macOS/Linux
# or
venv\Scripts\activate     # On Windows

# Install packages
pip install -r requirements.txt
```

## Usage

```bash
python app.py
```

The script will:
1. Load 4 WAV audio files (signal_1.wav through signal_4.wav)
2. Display time-domain representations of all signals
3. Scale the masking signals relative to the target signal
4. Generate visualization plots

## Key Functions

### `scaleMasker(target, masker)`
Scales a masking signal relative to a target signal for SNR control.

**Parameters:**
- `target`: Target speech signal (array)
- `masker`: Masking/noise signal (array)

**Returns:**
- `masker1`: Scaled masking signal

**Process:**
- Equalizes signal lengths
- Calculates scaling factor based on standard deviation ratio
- Returns scaled masker at specified SNR level

## Signal Description

- **Signal 1**: Target speech (clean speech signal to be analyzed/protected)
- **Signals 2, 3, 4**: Masking signals representing background noise or interference

## Output

The program generates matplotlib plots showing:
- 2×2 subplot grid of time-domain signals
- Individual signal waveforms with amplitude and time axes
- Clear labeling of target vs. masking signals

## Future Enhancements

- Frequency-domain analysis (FFT)
- Filter design and implementation
- Noise reduction algorithms
- Real-time audio processing
- Enhanced SNR calculations
- Export processed audio files

## Notes

- Ensure WAV files (signal_1.wav - signal_4.wav) are in the same directory as app.py
- Sample frequency is automatically detected from the WAV files
- All signals are processed with the same sample rate

## Author
[Your Name/Organization]

## Course
SEM 8 - Digital Signal Processing (DSP)

## License
[Your License Here]
