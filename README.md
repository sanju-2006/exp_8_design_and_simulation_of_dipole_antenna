# exp_8_design_and_simulation_of_dipole_antenna
Design and Simulation of a Halfwave Dipole Antenna using using Ansys HFSS
# Experiment 8 — Design and Simulation of a Half-Wave Dipole Antenna Using Ansys HFSS


---

## Aim

To design and simulate a half-wave dipole antenna at a specified resonant frequency using Ansys HFSS, and to study its return loss, VSWR, gain and radiation pattern.

## Software Used

Ansys HFSS (High Frequency Structure Simulator)

---

## Theory

A **dipole antenna** is one of the simplest and most widely used radiating structures, consisting of two straight conductors fed at the centre. When the total length of the dipole is half a wavelength (λ/2) at the operating frequency, it is called a **half-wave dipole**.

For a thin half-wave dipole:

```
Length, L = λ/2 = c / (2f)
```

where **c** is the velocity of light and **f** is the operating frequency.

Each arm of the dipole is therefore λ/4 long. In practice the physical length is slightly less than the calculated free-space value because of the end effect, so a **length reduction factor (k)**, typically 0.95, is applied:

```
L(effective) = k × (λ/2)
```

The radius of the dipole conductor is generally chosen such that L/d (length-to-diameter ratio) lies between 100 and 1000 for a thin-wire approximation to hold.

**Key characteristics of an ideal half-wave dipole:**

| Parameter | Typical value |
|---|---|
| Input impedance (free space) | ≈ 73 + j42.5 Ω |
| Directivity | ≈ 2.15 dBi |
| Radiation pattern (E-plane) | Figure-of-eight |
| Radiation pattern (H-plane) | Omnidirectional (circular) |
| Bandwidth | Narrow (few %) |

The antenna is usually fed at the centre gap using a **lumped port** or a **wave port**, and its performance is evaluated using the reflection coefficient (S11), VSWR, gain, directivity and 3-D radiation pattern obtained from the simulation.

---

## Design Specifications

| Parameter | Value |
|---|---|
| Operating frequency (f) | ______ GHz |
| Wavelength, λ = c/f | ______ mm |
| Dipole length, L = λ/2 | ______ mm |
| Arm length, L/2 | ______ mm |
| Conductor radius | ______ mm |
| Feed gap | ______ mm |
| Substrate / boundary | Radiation box (λ/4 air-buffer on all sides) |

---

## Procedure

1. **Launch Ansys HFSS** and create a new project. Insert an **HFSS Design** with solution type **Driven Modal**.
2. **Set the model units** to mm (or the unit convenient for the design).
3. **Draw the dipole:**
   - Create two cylinders (or thin rectangular strips) of radius *r* and length *L/2* each, placed along the Z-axis, separated by a small feed gap at the origin.
   - Assign the material as a **perfect conductor (PEC)** or copper.
4. **Assign the excitation:**
   - At the feed gap, create a small sheet/line and assign a **Lumped Port** (with an appropriate impedance line and resistance, typically 50 Ω) or a **Lumped RLC/Gap Source**.
5. **Create the radiation boundary:**
   - Draw an **air box** (vacuum) around the dipole, at least λ/4 away from the antenna in all directions.
   - Assign the outer surface of the air box as a **Radiation Boundary**.
6. **Set up the analysis:**
   - Add a **Solution Setup** with the solution frequency equal to the design frequency.
   - Add a **Frequency Sweep** (Fast/Interpolating) over the band of interest.
7. **Add radiation pattern reports:**
   - Insert a **Far Field Setup** (Infinite Sphere) to compute the 3-D radiation pattern.
8. **Validate and run the simulation** (Validation Check → Analyze All).
9. **Post-process the results:**
   - Plot **S11 (return loss)** vs frequency.
   - Plot **VSWR** vs frequency.
   - Plot the **2-D polar** and **3-D radiation patterns**.
   - Note the **gain**, **directivity** and **radiation efficiency** at the resonant frequency.

---

## Observations

<img width="525" height="880" alt="image" src="https://github.com/user-attachments/assets/2fd683a2-7d50-421e-8cc3-d33d4f5e27db" />


### Graphs
<img width="710" height="798" alt="image" src="https://github.com/user-attachments/assets/8f1bd96d-7865-4986-8b26-6dc63f968667" />

---

## Precautions

1. Ensure the radiation boundary is at least λ/4 away from the antenna structure on all sides to avoid reflection errors.
2. Mesh the model finely enough (especially near the feed gap) for accurate convergence.
3. Verify that the port impedance matches the intended feed impedance before analysing S11/VSWR.
4. Check for geometry validation errors before running the simulation.

## Result
 
Resonant Frequency = 2.4GHz

Return loss = -20dB

VSWR = 1.22

Gain = 2.15DBI
## Conclusion

A half-wave dipole antenna was designed and simulated at ______ GHz using Ansys HFSS.
