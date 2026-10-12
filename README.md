# Alpha Power: Eyes Open vs. Eyes Closed

## Question
Is occipital alpha power (8-12 Hz) higher with eyes closed than with eyes open?

## Data
Public PhysioNet EEG Motor Movement/Imagery dataset, loaded through MNE-Python.
10 subjects, 1-minute baseline recordings (run 1: eyes open, run 2: eyes closed).

## Methods
- Loaded the recordings and standardized channel names with MNE-Python
- Band-pass filtered 1-40 Hz
- Computed alpha power (8-12 Hz) averaged over occipital channels O1, Oz, O2
- Compared conditions with a paired t-test on raw power and on log10-transformed power
  (EEG power is right-skewed, so the log version is the better-justified test)

## Results
- Mean alpha power, eyes open: 25.90 µV²/Hz
- Mean alpha power, eyes closed: 290.77 µV²/Hz
- Raw power: t = [3.08], p = 0.0131
- Log-transformed power: t = 5.62, p = 0.0003

Alpha power was higher with eyes closed in 10 out of 10 subjects.
The analysis and figure are in the notebook in this repository.

## Limitations
- Only 10 subjects from a single public dataset
- No artifact rejection beyond filtering
- This is a well-established effect, so the project is a pipeline check, not a new finding

## Tools
Python, MNE-Python, NumPy, SciPy, Matplotlib (run in Google Colab)
