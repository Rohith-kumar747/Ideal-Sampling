# Ideal, Natural, & Flat-top -Sampling
# Aim
Write a simple Python program for the construction and reconstruction of ideal, natural, and flattop sampling.
# Tools required
Google colab ,
Python,
Numpy library,
Internal connection .
# Program
```
import numpy as np
import matplotlib.pyplot as plt
fm = 5                      # Message frequency 5hz
fs = 50                     # Sampling frequency 50hz
t = np.linspace(0, 1, 1000) # Continuous time axis
ts = np.arange(0, 1, 1/fs)  # Sampled time axis


x = np.sin(2 * np.pi * fm * t)#x=sin(2pifmt)


xs = np.sin(2 * np.pi * fm * ts)


flat_top = np.zeros_like(t)

for i in range(len(ts)-1):
    idx = np.where((t >= ts[i]) & (t < ts[i+1]))
    flat_top[idx] = xs[i]

plt.figure(figsize=(12,8))


plt.subplot(4,1,1)
plt.plot(t, x)
plt.title("Original Analog Signal")
plt.grid()


plt.subplot(4,1,2)
plt.stem(ts, xs, basefmt=" ")
plt.title("Ideal Sampling")
plt.grid()


plt.subplot(4,1,3)
plt.plot(t, x)
plt.stem(ts, xs, linefmt='r', markerfmt='ro', basefmt=" ")
plt.title("Natural Sampling")
plt.grid()


plt.subplot(4,1,4)
plt.plot(t, flat_top)
plt.title("Flat-top Sampling")
plt.grid()

plt.tight_layout()
plt.show()
```
# Output Waveform
  <img width="1477" height="984" alt="image" src="https://github.com/user-attachments/assets/3b68de22-e7d2-4763-97aa-62708b21a0f5" />

# Results

Python program for the construction and reconstruction of ideal, natural, and flattop sampling verified successfully.
