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


