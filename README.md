# Magnetic Field Effects in Pre-Equilibrium Dynamics

Code, data, and plots for analyzing magnetic field effects during the pre-equilibrium stage of relativistic heavy-ion collisions (RHIC and LHC energies).

## Repository structure

- **`B_field_profile/`** — Magnetic field time-profile data and fits for Au+Au (RHIC, 200 GeV) and Pb+Pb (LHC, 5.02 TeV) collisions across several centrality classes.
  - `Bfield_*.txt` — magnetic field strength vs. proper time, per system/centrality
  - `plot_B_profile_fits.py` — fits and plots the field profiles
  - `B_profile_fits.png` — resulting figure

- **`Compare-kurkela-zhu/`** — Comparison against digitized reference points from Kurkela & Zhu.
  - `kurkela_zhu_PL_points.txt`, `kurkela_zhu_PT_points.txt` — digitized longitudinal/transverse pressure points
  - `check_kurkela_digitized.py` — reproduces the comparison plot
  - `check_kurkela_digitized.png` — resulting figure

- **`LHC_PLPT_plots/`** — Longitudinal/transverse pressure ratio results at LHC energy.
  - `LHC_PLPT_lambda.py` — generates the plot
  - `LHC_PLPT_lambda.png` — resulting figure

- **`RHIC_PLPT_plots/`** — Longitudinal/transverse pressure ratio results at RHIC energy.
  - `RHIC_PLPT_lambda.py`, `RHIC_PLPT_xi.py` — generate the plots
  - `RHIC_PLPT_lambda.png`, `RHIC_PLPT_xi.png` — resulting figures

## Requirements

- Python 3
- `numpy`, `scipy`, `matplotlib`

## Changes

- **23 November 2026.** The initial distribution in `LHC_PLPT_plots/LHC_PLPT_lambda.py` is now normalized to the initial energy density, $\varepsilon_0 = (dE_T/dy)/(\tau_0 A_T)$, in place of the earlier saturation-based normalization. The same prefactor is used for $\lambda = 10$ and $\lambda = 0.1$. Because the rescaling is common to $P_L$ and $P_T$, the ratio $P_L/P_T$ is unaffected.
- **23 November 2026.** The same normalization is now used in `LHC_PLPT_plots/LHC_PLPT_xi.py`. The prefactor is fixed separately for each value of $\xi$, since the energy integral of the initial distribution depends on $\xi$. For $\xi = 10$, $4$ and $1$ the initial energy density is $478.261~\mathrm{GeV/fm^3}$ in all three cases. As before, $P_L/P_T$ is unaffected by this rescaling.

## Citation

If you use this code or data, please cite the associated paper (citation details to be added upon publication).

## License

MIT — see [LICENSE](LICENSE).
