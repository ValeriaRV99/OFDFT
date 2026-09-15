# OFDFT

A library of **local pseudopotentials for orbital-free DFT**, distributed in `psp8`
format, together with the web page that browses them.

Conventional Kohn-Sham pseudopotentials are nonlocal and cannot be used directly in
orbital-free DFT. The potentials here are built by targeting existing Kohn-Sham
pseudopotentials through an optimized effective potential procedure, giving local
pseudopotentials that stay accurate and transferable — including for transition
metals, where earlier local pseudopotentials perform poorly.

## Contents

```
PP_1/PP_1/      pseudopotential files (psp8), 57 in total
docs/           web page for browsing the library
index.htlm      root-level page
.github/        Actions workflow that deploys the page
```

## Naming

Files follow `<Element>_<variant>_<reference>.psp8`:

| Part | Meaning |
|---|---|
| `LPP` | local pseudopotential |
| `NLPP` | built to reproduce a nonlocal pseudopotential |
| `new` | current generation of the construction |
| `gbrv` | targets the GBRV reference set |
| `psl` | targets the PSLibrary reference set |
| `bcc` | fitted against the bcc phase |

Elements covered include Ag, Au, Cd, Co, Cr, Cu, Hf, Hg, Mo, Nb, Ni, P, Pd, Rh, Ta,
Ti, V, W, Zn and Zr — see `PP_1/PP_1/` for the full set.

## Usage

The `psp8` files are read directly by
[DFTpy](https://gitlab.com/pavanello-research-group/dftpy), e.g.

```python
PP_list = {'Ag': 'PP_1/PP_1/Ag_new.psp8'}
PSEUDO = Functional(type='PSEUDO', grid=grid, ions=ions, PP_list=PP_list)
```

## Citing

The construction and benchmarks are described in:

> V. Rios-Vargas, E. Oyeniyi, X. Shao, W. F. I. Elsayed, S. J. Ogenyi, A. Okello,
> M. Pavanello, "Pseudopotentials for orbital-free DFT: capturing nonlocality and
> correcting functional approximants", *Phys. Rev. B* **113**, 125124 (2026).
> [doi:10.1103/b9fg-k8tm](https://doi.org/10.1103/b9fg-k8tm) ·
> [arXiv:2511.19892](https://arxiv.org/abs/2511.19892)

## Related

- [OFPP](https://github.com/ValeriaRV99/OFPP) — pseudopotential browser
- [NLCC](https://github.com/ValeriaRV99/NLCC) — nonlinear core corrections
- [Li](https://github.com/ValeriaRV99/Li) — lithium local pseudopotentials
