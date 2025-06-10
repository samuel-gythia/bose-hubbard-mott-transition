# 🔵 Bose-Hubbard Mott Transition

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![SciPy](https://img.shields.io/badge/SciPy-1.7+-green.svg)](https://scipy.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.21+-red.svg)](https://numpy.org/)

> **Quantum many-body physics simulation of the Bose-Hubbard model featuring 2-site exact diagonalization spectrum analysis and 4-site number fluctuation dynamics across the Mott transition.**

## 🧬 Physical Foundation

The **Bose-Hubbard Hamiltonian** captures the fundamental quantum many-body physics of ultracold bosonic atoms in optical lattices:

```mathematica
Ĥ = -J ∑⟨i,j⟩ (b̂ᵢ†b̂ⱼ + h.c.) + (U/2) ∑ᵢ n̂ᵢ(n̂ᵢ-1) - μ ∑ᵢ n̂ᵢ
```

This model exhibits a **quantum phase transition** between:

- **🌊 Superfluid Phase** (J >> U): Delocalized atoms with global phase coherence
- **🔒 Mott Insulator Phase** (U >> J): Localized atoms with fixed integer occupancy
- **⚖️ Critical Point**: Quantum fluctuations drive the transition at (U/J)c ≈ 3.37

### Key Physics Explored:
- **Quantum Phase Transitions**: Zero-temperature transitions driven by quantum fluctuations
- **Many-Body Localization**: Competition between kinetic energy and interactions  
- **Finite-Size Scaling**: Universal critical behavior in small quantum systems
- **Number Fluctuations**: Order parameter characterizing the Mott insulating state

## ⚙️ Computational Methods

### **Exact Diagonalization Framework**
The simulation employs **exact diagonalization** to solve finite Bose-Hubbard systems with full quantum precision:

### 1. **Two-Site System** (2 bosons, 2 sites)
```python
# Fock basis: |n₁, n₂⟩ = {|2,0⟩, |1,1⟩, |0,2⟩}
H_matrix = construct_hamiltonian(U_over_J_ratio)
eigenvals, eigenvecs = np.linalg.eigh(H_matrix)
```
- **Hilbert Space**: 3-dimensional Fock basis
- **Observable**: Energy spectrum vs. U/J ratio
- **Physics**: Level crossing at the critical point

### 2. **Four-Site Chain** (4 bosons, 4 sites)  
```python
# Extended Fock space with hopping matrix elements
fluctuations = ⟨n²⟩ - ⟨n⟩²  # Number variance per site
```
- **Hilbert Space**: 35-dimensional (multinomial coefficients)
- **Observable**: Local number fluctuations ⟨Δn²⟩ᵢ
- **Physics**: Fluctuation suppression in Mott phase

## 📊 Results & Analysis

<div align="center">

### Energy Spectrum Evolution
![BH2 Spectrum](bloch_BH2_spectrum.png)
*Two-site energy levels showing avoided crossing at the quantum critical point*

### Number Fluctuation Dynamics
![BH4 Fluctuations](bloch_BH4_fluctuations.png)
*Four-site number variance demonstrating Mott insulator formation (U/J >> 1)*

</div>

### **Critical Observations**:
- **Energy Gap**: Opens at U/J ≈ 3.37 marking the transition
- **Fluctuation Suppression**: ⟨Δn²⟩ → 0 in the Mott phase  
- **Finite-Size Effects**: Discrete spectrum reveals quantum nature

## 🚀 Quick Start

```bash
# Clone repository
git clone https://github.com/samuel-gythia/bose-hubbard-mott-transition.git
cd bose-hubbard-mott-transition

# Install dependencies
pip install numpy scipy matplotlib jupyter

# Run simulation
jupyter notebook Bloch_MottTransition.ipynb
```

## 📚 Scientific References

- **Greiner, M.** et al. "Quantum phase transition from a superfluid to a Mott insulator in a gas of ultracold atoms," *Nature* **415**, 39 (2002). [DOI](https://doi.org/10.1038/415039a)
- **Jaksch, D.** et al. "Cold bosonic atoms in optical lattices," *Phys. Rev. Lett.* **81**, 3108 (1998).
- **Fisher, M. P. A.** et al. "Boson localization and the superfluid-insulator transition," *Phys. Rev. B* **40**, 546 (1989).

---
<div align="center">

**🔗 [View Simulation](https://github.com/samuel-gythia/bose-hubbard-mott-transition) | 📧 [Contact](https://github.com/samuel-gythia)**

</div>
  

## How to Run

```bash
conda activate qc-env
jupyter lab
```