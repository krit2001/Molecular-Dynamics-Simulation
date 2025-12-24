# PMF Calculation of K+ Conduction in KcsA Channel

**Author**: Krit Sharma  
**Course**: CHE622, IIT Kanpur  
**Tools**: GROMACS, Python, WHAM

## Abstract
This project reproduces the potential of mean force (PMF) calculations for potassium ion conduction through the KcsA selectivity filter, originally studied by Bernèche and Roux (2001). Using 1D Umbrella Sampling in GROMACS, we simulated the permeation of a K+ ion along the channel axis (Z-axis) to map the free energy landscape.

## Methodology
1. **System Preparation**: KcsA tetramer (PDB: 1K4C) embedded in a lipid bilayer.
2. **Equilibration**: Standard EM, NVT, and NPT protocols.
3. **Steered MD (Pulling)**: A single K+ ion was pulled through the filter to generate starting configurations.
4. **Umbrella Sampling**:
   - Windows spaced approx. 0.1 nm apart.
   - Harmonic biasing potential applied ($k \approx 1000$ kJ/mol/nm$^2$).
   - 100-200 ps simulation per window.
5. **Analysis**: PMF reconstruction using the Weighted Histogram Analysis Method (`gmx wham`).

## Results
The calculated PMF reveals energy wells corresponding to the S1, S3, and S4 binding sites, with a deep minimum at $Z \approx 5.8$ Å (likely the S0 site).
