# MSc Project — FBMC vs. OFDM Waveform Comparison

MATLAB simulations comparing **FBMC (Filter Bank Multicarrier)** against conventional **OFDM (Orthogonal Frequency Division Multiplexing)** as candidate waveforms for next-generation (5G) wireless systems.

The study evaluates both modulation schemes across four dimensions:

- **BER vs. Eb/N0** — bit error rate performance over AWGN
- **PSD** — power spectral density / out-of-band emission
- **PAPR** — peak-to-average power ratio
- **Constellation diagram** — signal quality visualization

## Background

OFDM is the dominant waveform in 4G/LTE, but suffers from high out-of-band leakage and requires a cyclic prefix. FBMC applies a per-subcarrier prototype filter combined with **OQAM (Offset QAM)** to achieve much lower spectral sidelobes and better spectral efficiency (no cyclic prefix), at the cost of higher implementation complexity. This project quantifies those trade-offs through simulation.

## Repository Structure

### FBMC scripts
| File | Purpose |
|------|---------|
| `FBMC_prototype_filter.m` | Prototype (PHYDYAS) filter design |
| `FBMC_OQAM_consteallation_diagram.m` | OQAM constellation diagram |
| `FBMC_BERvsEbN0_OQAM.m` | BER vs. Eb/N0 performance |
| `FBMC_PSD.m` | Power spectral density |
| `FBMC_PAPR.m` | Peak-to-average power ratio |

### OFDM scripts
| File | Purpose |
|------|---------|
| `OFDM_subcarrier_index.m` | Subcarrier index mapping |
| `OFDM_consteallation_diagram.m` | Constellation diagram |
| `OFDM_BERvsEbN0.m` | BER vs. Eb/N0 performance |
| `OFDM_PSD.m` | Power spectral density |
| `OFDM_PAPR.m` | Peak-to-average power ratio |

### Comparison scripts
| File | Purpose |
|------|---------|
| `BERvsEbN0_comparison_FBMC_OFDM.m` | Side-by-side BER comparison |
| `PAPR_FBMC_OFDM.m` | Side-by-side PAPR comparison |

## Requirements

- MATLAB (R2015 or later recommended)
- Signal Processing Toolbox

## Usage

Open MATLAB, set this folder as the working directory, and run any script directly, e.g.:

```matlab
% Compare BER performance of FBMC and OFDM
BERvsEbN0_comparison_FBMC_OFDM

% Compare PAPR of FBMC and OFDM
PAPR_FBMC_OFDM
```

Each script generates its own figure(s). Simulation parameters (number of subcarriers, modulation order, SNR range, number of symbols) are defined at the top of each file and can be adjusted as needed.

## License

Academic MSc project — provided for educational and research reference.
