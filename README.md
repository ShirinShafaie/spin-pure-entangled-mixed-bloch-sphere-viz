# Quantum Spin States: Bloch Sphere Visualisation

Interactive visualisation for spin-½ quantum systems using the Bloch sphere representation.

## Methodology

Seven interactive visualisations covering observables, superposition, entanglement, classical mixtures, and time evolution under magnetic fields.
Conceptual design and mathematical verification: Shirin Shafaie. Code and numerical implementation: collaboration with Claude Sonnet 4.5

**Mathematical Foundation:**

The Bloch sphere is the canonical representation of projective Hilbert space ℂℙ¹ as S²:

```
|ψ⟩ = cos(θ/2)|0⟩ + e^(iφ)sin(θ/2)|1⟩  ↦  r = (⟨σ₁⟩, ⟨σ₂⟩, ⟨σ₃⟩)
```

- Pure states: surface (|r| = 1, Tr(ρ²) = 1)
- Mixed states: interior (|r| < 1, Tr(ρ²) < 1)
- Time evolution: rotation about field axis with angular velocity 2B

**Key Insight (Exercise 1.5):**

Three states with identical local density matrix ρ = I/2:

1. **Pure superposition**: Surface point, Tr(ρ²) = 1
2. **Entangled (reduced)**: ρ = Tr₂(|Ψ⟩⟨Ψ|), quantum correlations
3. **Classically mixed**: ρ = Σ pᵢ|ψᵢ⟩⟨ψᵢ|, statistical ensemble

Cases 2 and 3 are locally indistinguishable but differ in mathematical origin.

---

## Features

**Static (Exercises 1.1–1.5):**
- Measurement axis control
- State vector visualisation
- Three-way comparison with purity labels

**Dynamic (Exercises 1.6–1.7):**
- Initial state control (θ, φ sliders)
- Time evolution animation
- Magnetic field adjustment
- Real-time trace recording
- Frequency doubling demonstration (SU(2) → SO(3) covering)

---

## Technical

**Stack:**
- Three.js r128 (WebGL)
- Custom complex number arithmetic
- Pauli matrix operations

**Coordinate Mapping:**
```javascript
blochToThree(x, y, z) → (x, z, -y)
```

Camera at [3.5, 2, -3.5] ensures proper axis orientation: +X right, -i left, |0⟩ top.

**File:** Self-contained HTML with CDN dependencies.

---

## Resources

1. Gualtieri, M. lectures and lecture notes, "Geometry of Quantum Mechanics" (Fields Institute, 2025)
2. Watrous, J. "Quantum Information & Computation" (IBM Quantum Course, density matrices module)
3. Nielsen, M. A. & Chuang, I. L. *Quantum Computation and Quantum Information* (Cambridge University Press, 2000), Chapters 2.1–2.2
4. Born, M. "The Statistical Interpretation of Quantum Mechanics" (Nobel Lecture, 1954)
5. Dirac, P. A. M. "Lecture 1: Quantum Mechanics" (Christchurch, New Zealand, 1975)
6. Connes, A. *Noncommutative Geometry* (Academic Press, 1994), Chapter 1.1
7. Fulton, W. & Harris, J. *Representation Theory: A First Course* (Springer GTM 129, 1991), Lectures 8 and 11.1
