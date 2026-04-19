# Tall Building Preliminary Structural Analysis Framework (SDOF + MDOF)

## Overview

This project presents a **computational structural framework** for the preliminary design and dynamic assessment of tall buildings. The tool integrates:

- Global **single-degree-of-freedom (SDOF)** estimation  
- Refined **multi-degree-of-freedom (MDOF)** modal analysis  
- Automated preliminary sizing of structural components  
- Visualization of the **first five mode shapes**

The framework is intended for **conceptual design, comparative studies, and research-oriented analysis**, rather than detailed code-based final design.

---

## Key Features

- Support for **square and triangular plan configurations**
- Inclusion of:
  - Central core shear walls  
  - Distributed perimeter shear walls  
  - Basement retaining walls  
- Adaptive sizing of:
  - Columns (corner, perimeter, interior)
  - Beams and slabs
- Estimation of:
  - Structural weight
  - Global stiffness
  - Drift response
- Dynamic analysis:
  - Fundamental period (SDOF)
  - First **5 natural periods and mode shapes (MDOF)**

---

## Theoretical Background

### 1. SDOF Approximation

The global structural period is estimated using:

T = 2π √(M / K)

where:
- M = effective modal mass  
- K = equivalent lateral stiffness  

This provides a rapid estimate consistent with design code formulations.

---

### 2. MDOF Modal Analysis

The structure is modeled as a **lumped-mass shear building**, governed by:

[K]{φ} = ω²[M]{φ}

where:
- K = global stiffness matrix  
- M = mass matrix  
- φ = mode shape vector  
- ω = circular frequency  

The solution yields:
- Natural frequencies  
- Modal periods  
- Mode shapes  

---

### 3. Stiffness Calibration (Critical Improvement)

A key aspect of this framework is the **consistency between SDOF and MDOF representations**.

The story stiffness distribution is calibrated such that:

K_equivalent ≈ K_estimated

This is achieved by enforcing a **series-equivalent stiffness condition**:

1 / K_total = Σ (1 / k_i)

This ensures:
- Physically consistent modal response  
- Accurate estimation of the fundamental period  
- Elimination of artificial period inflation  

---

<img width="1280" height="759" alt="1" src="https://github.com/user-attachments/assets/0bc6cd80-87c6-4010-baf6-ced502f368c1" />

<img width="1278" height="768" alt="2" src="https://github.com/user-attachments/assets/f43279e2-fe9a-4081-aae3-2d632d66100c" />

<img width="1280" height="759" alt="3" src="https://github.com/user-attachments/assets/5f385c08-c75a-4180-92ef-565a27b870c8" />

<img width="1280" height="764" alt="4" src="https://github.com/user-attachments/assets/73dc6600-5f07-41bc-9c04-eaf4c9d4a642" />


<img width="620" height="674" alt="Screenshot 2026-04-13 185309" src="https://github.com/user-attachments/assets/772476a3-6770-43c1-bcaf-8e23ea4718c7" />
