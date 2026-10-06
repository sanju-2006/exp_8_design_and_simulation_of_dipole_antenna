# Experiment 8 — Design and Simulation of a Half-Wave Dipole Antenna Using Ansys HFSS

## Aim
To design and simulate a half-wave dipole antenna at a specified resonant frequency using Ansys HFSS, and to study its return loss, VSWR, gain and radiation pattern.

## Software Used
Ansys HFSS (High Frequency Structure Simulator)

## Theory
A dipole antenna is one of the simplest and most widely used radiating structures, consisting of two straight conductors fed at the centre. When the total length of the dipole is half a wavelength (λ/2) at the operating frequency, it is called a half-wave dipole.

For a thin half-wave dipole:

**Length, L = λ/2 = c / (2f)**

where c is the velocity of light and f is the operating frequency.

Each arm of the dipole is therefore λ/4 long. In practice the physical length is slightly less than the calculated free-space value because of the end effect, so a length reduction factor (k), typically 0.95, is applied:

**L(effective) = k × (λ/2)**

The radius of the dipole conductor is generally chosen such that L/d (length-to-diameter ratio) lies between 100 and 1000 for a thin-wire approximation to hold.

Key characteristics of an ideal half-wave dipole:

| Parameter | Typical value |
|---|---|
| Input impedance (free space) | ≈ 73 + j42.5 Ω |
| Directivity | ≈ 2.15 dBi |
| Radiation pattern (E-plane) | Figure-of-eight |
| Radiation pattern (H-plane) | Omnidirectional (circular) |
| Bandwidth | Narrow (few %) |

The antenna is usually fed at the centre gap using a lumped port or a wave port, and its performance is evaluated using the reflection coefficient (S11), VSWR, gain, directivity and 3-D radiation pattern obtained from the simulation.

## Design Specifications

| Parameter | Value |
|---|---|
| Operating frequency (f) | 2.4 GHz |
| Wavelength, λ = c/f | 125 mm |
| Dipole length, L = λ/2 | 62.5 mm |
| Effective length, k × (λ/2) with k = 0.95 | 59.4 mm |
| Arm length, L/2 | 29.2 mm |
| Conductor radius | 0.25 mm |
| Feed gap | 1 mm |
| Material | PEC |
| Port | Lumped port, 50 Ω |
| Substrate / boundary | Radiation box (λ/4 = 31.25 mm air-buffer on all sides), approx. 63 × 63 × 122 mm |
| Solution frequency | 2.4 GHz |
| Frequency sweep | 1.5 GHz to 3.5 GHz, step 0.01 GHz |

## Procedure
1. Launch Ansys HFSS and create a new project. Insert an HFSS Design with solution type **Driven Modal**.
2. Set the model units to mm (or the unit convenient for the design).
3. Draw the dipole:
   - Create two cylinders (or thin rectangular strips) of radius r = 0.25 mm and length L/2 = 29.2 mm each, placed along the Z-axis, separated by a 1 mm feed gap at the origin.
   - Assign the material as a perfect conductor (PEC) or copper.
4. Assign the excitation:
   - At the feed gap, create a small sheet/line and assign a **Lumped Port** (with an appropriate impedance line and resistance, typically 50 Ω) or a Lumped RLC/Gap Source.
5. Create the radiation boundary:
   - Draw an air box (vacuum) around the dipole, at least λ/4 away from the antenna in all directions.
   - Assign the outer surface of the air box as a **Radiation Boundary**.
6. Set up the analysis:
   - Add a Solution Setup with the solution frequency equal to the design frequency (2.4 GHz).
   - Add a Frequency Sweep (Fast/Interpolating) over the band of interest (1.5 to 3.5 GHz).
7. Add radiation pattern reports:
   - Insert a Far Field Setup (Infinite Sphere) to compute the 3-D radiation pattern.
8. Validate and run the simulation (Validation Check → Analyze All).
9. Post-process the results:
   - Plot S11 (return loss) vs frequency.
   - Plot VSWR vs frequency.
   - Plot the 2-D polar and 3-D radiation patterns.
   - Note the gain, directivity and radiation efficiency at the resonant frequency.

## Observations

| Quantity | Observed value |
|---|---|
| Resonant frequency | 2.40 GHz |
| Return loss (S11) | −18 dB |
| VSWR | 1.28 |
| Gain | 2.1 dBi |
| Directivity | 2.15 dBi |
| Radiation efficiency | ≈ 99% |
| Bandwidth (S11 < −10 dB) | ≈ 250 MHz (about 10%) |
| Input impedance | ≈ 68 Ω |

## Graphs

<img width="1200" height="1600" alt="WhatsApp Image 2026-09-19 at 10 38 51 AM (2)" src="https://github.com/user-attachments/assets/56284614-1c10-47f0-9b5c-b435b2e68cf3" />
<img width="1200" height="1600" alt="WhatsApp Image 2026-09-19 at 10 38 51 AM (1)" src="https://github.com/user-attachments/assets/afbd2536-3db4-4e11-91dc-898c6a4ee240" />

## Precautions
- Ensure the radiation boundary is at least λ/4 away from the antenna structure on all sides to avoid reflection errors.
- Mesh the model finely enough (especially near the feed gap) for accurate convergence.
- Verify that the port impedance matches the intended feed impedance before analysing S11/VSWR.
- Check for geometry validation errors before running the simulation.

## Result
- **Resonant Frequency** = 2.4 GHz
- **Return loss** = −18 dB
- **VSWR** = 1.28
- **Gain** = 2.1 dBi

## Conclusion
A half-wave dipole antenna was designed and simulated at 2.4 GHz using Ansys HFSS. The antenna resonated at about 2.4 GHz with a return loss below −10 dB and a VSWR below 2, showing a good impedance match to the 50 Ω port. The simulated gain of about 2.1 dBi agrees with the theoretical 2.15 dBi. The radiation pattern was figure-of-eight in the E-plane and omnidirectional in the H-plane, as expected for a half-wave dipole.
