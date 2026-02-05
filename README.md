# Gaussian-Pulse-Propagation
# Broadening of Gaussian Pulses

## Objective
Compare the results predicted by the linear system model of an optical fiber with the results of simulation.

---

## Theory
An optical fiber can be represented approximately by a linear system with an impulse response \(h(t)\) or a transfer function \(H(j\omega)\).  

If the optical source has a spectral width much greater than the signal bandwidth (e.g., the source is a directly modulated laser diode) and the operating wavelength is far from the zero-dispersion wavelength, then \(H(j\omega)\) is approximately Gaussian:

\[
H(\omega) = \exp(-\omega^2 T_F^2)
\]

where \(T_F\) is the RMS width of the impulse response, given approximately by:

\[
T_F = D(\lambda) \cdot L \cdot \Delta \lambda
\]

- \(L\): fiber length  
- \(D(\lambda)\): fiber dispersion coefficient  
- \(\Delta \lambda\): RMS spectral width of the optical source  

---

### Chirped Gaussian Pulse
A chirped Gaussian pulse can represent the output of a directly modulated laser diode. It is characterized by:
- RMS pulse width: \(T_{in}\)  
- Chirp factor: \(C\)  

The RMS pulse width relates to the FWHM pulse width:

\[
T_{in} = \frac{T_{FWHM}}{1.665}
\]

The RMS spectral width of the pulse is:

\[
\Delta \lambda = \frac{\lambda^2}{\pi c T_{in}} \sqrt{1 + C^2}
\]

where:
- \(\lambda\): operating wavelength  
- \(c\): speed of light  

---

### Output Pulse Broadening
If a Gaussian pulse is input to a linear system with a Gaussian impulse response, the output is also Gaussian with RMS width:

\[
T_{out}^2 = T_{in}^2 + T_F^2
\]

---

## Calculations
**System Parameters:**

| Component | Parameter | Value |
|-----------|-----------|-------|
| Transmitter – Gaussian Pulse Generator | Operating wavelength | 1550 nm |
| | Bit rate | 2.5 Gb/s |
| | FWHM pulse width | 0.5 bit period |
| | Chirp factor | -6 |
| Fiber | Type | Corning SMF-28 |
| | Length | 50 km |

**Required Calculations:**
- RMS width of transmitted pulse (\(T_{in}\))  
- RMS spectral width of transmitted pulse (\(\Delta \lambda\))  
- RMS width of fiber impulse response (\(T_F\))  
- RMS width of pulse at fiber far end (\(T_{out}\))  

---

## Layout
Place and connect the following components:
1. **User-defined bit sequence generator** – set to generate a single pulse of the specified width  
2. **Optical Gaussian pulse generator** – enter the chirp factor as a negative number  
3. **Optical fiber** – set according to specifications  
4. **Optical spectrum analyzers** and **optical time domain visualizers** at input and output of fiber  

---

## Simulation
- Set the parameters and run the simulation.  
- Use the visualizer displays to measure:  
  - FWHM width of input and output pulses  
  - FWHM width of optical spectra  

---

## Analysis
Compare the simulation results with the theoretical calculations and discuss any observed differences.
