\# ╔════════════════════════════════════════════════════════════════════════════╗

\# ║                                                                            ║

\# ║          Multiscale Thermal Modeling of Anisotropic Composite Materials    ║

\# ║                                                                            ║

\# ╚════════════════════════════════════════════════════════════════════════════╝



Advanced finite element simulation of heat transfer in anisotropic composites using FEniCS



\[!\[Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python\&logoColor=white)](https://www.python.org/)

\[!\[FEniCS](https://img.shields.io/badge/FEniCS-2019.2.0-orange)](https://fenicsproject.org/)

\[!\[License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

\[!\[DOI](https://img.shields.io/badge/DOI-pending-blue)](https://doi.org/...)



This repository provides an object-oriented Python implementation for multiscale thermal modeling of anisotropic composite structures, built on the FEniCS/Dolfin platform.



It supports arbitrary anisotropic thermal conductivity tensors, complex geometries via Gmsh, and post-processing/visualization with PyVista.



**## Recommended Execution Environment**



The project is \*\*primarily developed and optimized for Linux-based systems\*\*. All core development, testing, debugging, and performance benchmarking were performed on Linux. The following configurations are recommended:



\- \*\*Preferred OS\*\*: Ubuntu 20.04 / 22.04 LTS (or any recent Debian-based distribution)

\- \*\*Alternative (strongly recommended for Windows users)\*\*: Windows 11 + WSL2 (Windows Subsystem for Linux) with Ubuntu distribution

\- \*\*Why Linux / WSL2?\*\*

&nbsp; - Native support for FEniCS and its dependencies

&nbsp; 



The code has been tested on Windows 11 natively, but Linux (native or via WSL2) remains the most stable and efficient environment for running both phases of the workflow.



**## Features**



\- Full anisotropic thermal conductivity support (full 3×3 tensor)

\- Gmsh + meshio pipeline for high-quality mesh generation

\- Object-oriented solver design (easy to extend for multiphysics)

\- PyVista-based interactive 3D visualization of temperature fields

\- Modular class structure for material properties, boundary conditions and solvers



**## System Configuration (Tested on)**



\- OS: Windows 11 Pro 64-bit (Build 26200) + WSL2 Ubuntu

\- Hardware: OMEN by HP Gaming Laptop 16-wd0xxx

\- CPU: 13th Gen Intel Core i5-13420H (12 cores, ~2.1 GHz base)

\- RAM: 16 GB



**## Software Requirements**



| Package       | Version / Notes                          | Purpose                          |

|---------------|------------------------------------------|----------------------------------|

| FEniCS (DOLFIN) | 2019.2.0.dev0                           | Finite element solver            |

| gmsh          | latest                                   | Mesh generation                  |

| meshio        | ≥4.0                                     | Mesh format conversion           |

| pyvista       | latest                                   | 3D visualization and rendering   |

| numpy         | latest                                   | Array operations                 |

| scipy         | latest                                   | Sparse solvers and utilities     |



Note: DirectX 12 support is required for smooth PyVista rendering on Windows.







**\*\*Important two-phase execution order\*\***



This project is structured in two sequential phases to ensure correct data flow and avoid path-related issues:



**1. \*\*Phase 1\*\* – Run first (pre-processing / mesh \& data preparation)**  

   **```bash**

&nbsp;    (jupiter) Project Phase 1

&nbsp;   This step generates necessary mesh files, material data, or intermediate results required by Phase 2.



**Phase 2 – Run only after Phase 1 has completed successfully**

