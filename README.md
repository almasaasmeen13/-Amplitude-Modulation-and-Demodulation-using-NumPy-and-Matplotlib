# -Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib

__Aim__: 

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

__Apparatus Required__: 

Software: Python with NumPy and Matplotlib libraries 
Hardware: Personal Computer 

__Theory__: 

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting 
information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of 
the message signal. The general form of an AM signal is: 


__Algorithm__:
1. Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency. 
2. Generate Time Axis: Create a time vector for the signal duration. 
3. Generate Message Signal: Define the message signal as a cosine wave. 
4. Generate Carrier Signal: Define the carrier signal as a cosine wave. 
5. Modulate Signal: Apply the AM formula to obtain the modulated signal. 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

### PROGRAM :
~~~
import numpy as np
import matplotlib.pyplot as plt

# Parameters
Am = 13.4      # Message amplitude
Ac = 26.8       # Carrier amplitude
fm = 460       # Message frequency
fc = 4600        # Carrier frequency
fs = 20000      # Sampling frequency (must be high for smooth signal)

t = np.arange(0, 0.01, 1/fs)   # Time vector

# Message Signal
message = Am * np.cos(2 * np.pi * fm * t)

# Carrier Signal
carrier = Ac * np.cos(2 * np.pi * fc * t)

# Modulation Index
m = Am / Ac

# AM Modulated Signal
am_signal = Ac * (1 + m * np.cos(2 * np.pi * fm * t)) * np.cos(2 * np.pi * fc * t)

# Demodulation (Envelope Detector)
demodulated = np.abs(am_signal)

# Plotting
plt.figure(figsize=(12,10))

plt.subplot(4,1,1)
plt.plot(t, message)
plt.title("Message Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(4,1,2)
plt.plot(t, carrier)
plt.title("Carrier Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(4,1,3)
plt.plot(t, am_signal)
plt.title("AM Modulated Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(4,1,4)
plt.plot(t, demodulated)
plt.title("Demodulated Signal (Envelope)")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.tight_layout()
plt.show()
~~~
 __Output__:
<img width="1572" height="1198" alt="image" src="https://github.com/user-attachments/assets/90bda770-0979-445c-a430-b63c60b125a9" />


 __Result__:
 ![WhatsApp Image 2025-11-24 at 20 17 12_8d6783ee](https://github.com/user-attachments/assets/a8eb8b44-1c84-4d8e-98ea-1b8ca1eb46fa)



