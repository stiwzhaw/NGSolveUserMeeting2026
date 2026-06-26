# Abstracts
## ngsVEM: A Lightning Virtual Element Method Library for NGSolve

Umberto Zerbinati<br>
University of Oxford

ngsVEM is an NGSolve add-on for solving PDEs on polygonal meshes using the Lightning Virtual Element Method. By approximating virtual basis functions with rational functions, the method avoids the projection and stabilization procedures typical of classical VEM. We present the main ideas behind the method, its implementation within NGSolve, and numerical examples illustrating its accuracy and flexibility on polygonal meshes.

## NGSTrefftz: Recent Developments

Paul Stocker<br>
University of Vienna

NGSTrefftz is an NGSolve extension for Trefftz finite element methods, including built-in Trefftz spaces, tent-pitched Trefftz-DG methods, and embedded Trefftz methods. This talk presents recent developments concerning anisotropic meshes, preconditioning, and nonlinear problems such as Navier-Stokes.

## Coreform Cubit Integration with NGSolve (Online)

Kengo Sugahara<br>
Kindai University

We present an open-source integration of Coreform Cubit with NGSolve for accelerator electromagnet design, available via pip install radia. The key contribution is a CallbackGeometry API that directly queries the ACIS kernel for high-order hex mesh curving, eliminating STEP/OCC intermediate files. A netgen fork extending the SetGeomInfo API enables this Cubit-NGSolve mesh pipeline. The framework also provides Periodic Kelvin transformation for exact open-boundary conditions, mesh-free coil modeling via RadiaField CoefficientFunction (analytical Biot-Savart), and nonlinear magnetostatic solvers (Omega-reduced and A-formulation) with support for BH curves and hysteresis. Interactive Cubit GUI panels allow one-click solver execution. We demonstrate the solver on accelerator dipole magnet models.

## Bi-directional Weak Coupling of Integral Element Method and NGSolve for Magnetic Levitation Analysis (Online)

Takaaki Yano<br>
Kindai University

This presentation proposes a bi-directional weak coupling framework between an Integral Element Method (IEM) field source library and NGSolve for the electromagnetic analysis of magnetic levitation systems. While FEM is a powerful tool for electromagnetic analysis, it typically requires artificial boundary conditions for open-domain problems and entails high computational overhead due to frequent remeshing in moving-object simulations. Conversely, the IEM naturally handles open boundaries without the need for air-region meshing. To address these limitations, the proposed framework directly embeds IEM-computed external fields—specifically the magnetic vector potential $\vec{A}_{ext}$ and magnetic field intensity $\vec{H}_{ext}$—into the FEM weak form as external excitation. This approach eliminates the need for both field interpolation and remeshing for moving objects, enabling precise transient analysis on a fixed FEM mesh. The developed coupling framework is implemented and available at: https://github.com/ksugahar/Radia.

## Coupled Finite Element Modeling of Ground Heat Recovery with Ice Formation

Camilo Tello Fachin<br>
aramiko GmbH

Ground source heat pump (GSHP) systems require reliable performance predictions over decades. While conventional borehole heat exchangers and ground collectors are designed to keep soil temperatures above freezing, specialized systems either accept ice formation or actively operate in the phase change regime. These conditions fundamentally alter thermal behavior and soil moisture. Standard simulation tools cannot capture these effects.

We present a coupled finite element model for thermo-hydraulic flow with ice-water phase transitions in porous media with embedded pipe heat exchangers. The model couples the Richards equation for unsaturated flow with advective-diffusive heat transport, using an enthalpy formulation that captures latent heat effects from temperature changes and cryosuction. Constitutive relations follow established formulations (van Genuchten, Mualem, Clapeyron) from permafrost literature.

A novel 1D-3D coupling approach embeds 1D pipe networks in 3D soil domains using conforming meshes and interface heat exchange conditions. The implementation in NGSolve, an open-source finite element library, provides high-order accuracy and parallelism. Numerical verification confirms mass and energy conservation across freeze-thaw cycles with robust Newton convergence.

The framework enables quantitative assessment of ice formation impacts on GSHP performance, supports ice-aware control, and exploration of seasonal thermal storage exploiting latent heat of soil ice.

## Multiphysics Finite Element Simulation of Hybrid Electrical Tomography

Alberto Battistel<br>
Furtwangen University, Germany

Electrical impedance tomography (EIT) is a well-established imaging technique that enables real-time visualization of physiological processes due to its high temporal resolution, but it suffers from inherently low spatial resolution. Hybrid approaches aim to overcome this limitation by coupling electrical measurements with additional physical effects such as magnetic fields or locally induced mechanical motion. Examples include magneto-acoustic impedance tomography, Lorentz force impedance tomography, and acousto-electric tomography, which exploit interactions between electrical currents, magnetic fields, and acoustic or mechanical perturbations to improve spatial localization. In this work, we employ the finite element framework NGSolve to simulate these coupled physical interactions in biological tissues, providing a flexible computational environment for investigating both classical EIT and emerging hybrid tomographic modalities.

## Wave propagation in non-Newtonian media

Juan Pablo Carbajal, Reza Housseini<br>
OST Eastern Switzerland University of Applied Sciences

This talk explores wave propagation in non-Newtonian media using the Finite Element Method (FEM) with the NG solver. Beginning with one-dimensional simulations, we incrementally increase dimensionality and complexity, incorporating elements such as thinning and thickening media, and Stokes flow. Our explorative approach aims to deepen understanding of wave behavior in complex media systems.

## State-Space Concatenation of Reduced Finite Element Models for Accelerator Structures

Sosoho-Abasi Udongwo<br>
Brandenburgische Technische Universität Cottbus-Senftenberg

The electromagnetic simulation of large accelerator structures, such as RF cavity chains, is computationally demanding due to the high number of degrees of freedom required by the finite element methods (FEM). This work presents a framework that combines Model-Order Reduction (MOR) with state-space concatenation (SSC) within the NGSolve finite element environment. Individual cavity segments are discretised using high-order FEM, reduced to compact state-space models, and coupled through continuity conditions at shared interfaces to construct larger accelerator assemblies at significantly lower computational cost. A TESLA cavity chain is used as a test example to demonstrate reductions of several orders of magnitude in system size while maintaining excellent agreement with reference simulations from CST Studio Suite. The proposed methodology provides a scalable and computationally efficient approach for the simulation and design of large accelerator structures.

## Releasing the pressure for Surface Navier-Stokes

Tim van Beeck<br>
University of Göttingen

We present a discretization of incompressible flows on surfaces with arbitrary topology that avoids a saddle-point formulation. The formulation is based on a discrete Helmholtz--Hodge decomposition that splits the divergence-free subspace of the BDM space into the rotated gradient of a stream function and a finite-dimensional space of discrete harmonic fields whose dimension equals the first Betti number of the surface. We demonstrate the implementation of this splitting in NGSolve and apply it to the discretization of the incompressible Navier--Stokes equations on surfaces.

## Efficient Computational Simulation of Floor-Borne Vibrations in Magnet Resonance Imaging Scanners

Yashwanth Sooriyakanthan<br>
Swansea University

Magnetic Resonance Imaging (MRI) scanners deliver detailed images of soft tissues, bones, and internal organs for medical diagnosis. The main coils are superconductors, which generate a strong static background magnetic field across the bore of the magnet and aligns the protons in a human body's water molecules. This is perturbed by a time-varying field produced by x, y and z gradient coils, which ensure the magnetic field strength change predictably with location and are used in the imaging process. The conducing shields prevent external field interference. However, MRI scanners are highly sensitive to external vibrations, particularly floor-borne vibrations (FBVs), which can lead to image distortion or artefacts, known as ‘ghosting’. Simulating the impact of these vibrations is challenging, as current three-dimensional transient solvers, widely used in the industry, cannot produce results within an industrially viable timeframe. To address this, we are developing new accurate efficient simulation methods.

Our group has previously developed a computational framework for the simulation of the coupled magneto-mechanical problem in MATLAB, obtaining vibrations and induced stresses in the conducting components due to the eddy currents. Additionally reduced order models and Neural Networks were also developed to improve efficiency of output computation. We have developed a new computational framework using the python package NGSolve and high order finite elements, for solving the electro-magneto-mechanical problem in the frequency and transient domains for axisymmetric industrially motivated geometries, which we will review in the talk. The transient implementation includes a range of time-stepping schemes and fixed-point iteration acceleration for coupling physics. This allows the computation of nonlinear coupling terms, which is not feasible in the time-harmonic framework, providing a more accurate representation of the underlying physics and prediction of FBVs. The talk will also present our latest work towards extending this work to industrially relevant full three-dimensional geometries and FBV predictions.


## Simulating a rotating fan in a heat-pump unit with NGSolve: an MCS–IPCS solver

Christopher Lackner<br>
CERBSim

We present a solver for incompressible, high-Reynolds-number flow around a rotating fan, built on NGSolve and aimed at the design of heat-pump units. The flow is discretised with a mass-conserving mixed stress (MCS) method in H(div), giving pointwise divergence-free velocities, and advanced in time by an incremental pressure-correction (IPCS) splitting: an implicit MCS viscous step, a matrix-free upwind-DG convection step run on the GPU, and a hybridised mixed-Poisson pressure projection. Rotor and stator are meshed independently and coupled across a non-matching sliding interface using mortar methods, rebuilt each step for the velocity, pressure-trace and upwind-flux couplings.

We validate the method on a fan in a wall mount and then apply it to a full heat-pump unit, with a detailed fan and a homogenised heat exchanger. We close with an outlook on reinforcement-learning-driven design of a robust, parametrised flow rectifier.

* Joint work with the FFG-funded consortium (SCCH Hagenberg, TU Wien, Windpuls, EBM-papst, IDM Wärmepumpen).

## Solving a Heat-Flow system using NGSolve

Alexandre Tyl<br>
CERBSim / ENSTA Paris

n addition to the study of electromagnetic phenomena inside an electric transformer, the coupled heat-flow equations, regarding the oil inside the transformer, are an important and challenging question. This presentation outlines the development of a solver for the coupled heat equation and Navier–Stokes equations in the turret of an electric transformer, implemented in 2D using NGSolve.
Starting from a naive Galerkin method, different methods were implemented over time to stabilize and optimize the solver. Based on the obtained results, the HDG method was implemented to stabilize the system and address the heat equation, whereas the MCS method was chosen for the Navier–Stokes equations to guarantee a divergence-free velocity field.
The final solver provides an efficient way to simulate and solve the coupled thermal-fluid problem and can then be used to quantify heat flow costs due to electromagnetic  losses inside the transformer turret. The next step of the project would be the extension of the solver to solve similar 3D problems.

## WebGPU - Successor to webgui

Matthias Hochsteger, Christopher Lackner<br>
CERBSim

We present ngsolve_webgpu, a new GPU-native visualization stack for NGSolve and the planned replacement for webgui. Built on WebGPU, the modern successor to WebGL, it keeps the familiar Draw(cf, mesh, ...) interface while moving both rendering and computation onto the GPU: true high-order fields, clipping-plane cross-sections, streamlines and isosurfaces, complex-field phase animation, and export to standalone HTML for sharing.

This talk is a live, demo-driven tour of the new engine and its NGSolve integration.

## ngapp + ngsolve_gui

Christopher Lackner, Matthias Hochsteger<br>
CERBSim

NGSolve simulations usually live in scripts that are hard to hand to anyone who didn't write them. ngapp is a Python framework for wrapping such a script in a small, interactive web app: you build the UI from components — inputs, layout, tables, 3D viewports, plots — in Python, and Python state and the browser stay in sync automatically through reactive components and event callbacks. The same app runs locally with hot reload, deploys to GitHub Pages as a client-side static page, or installs as a standalone Python package.

ngsolve_gui is a GPU-based GUI for Netgen/NGSolve built on ngapp and ngsolve_webgpu. Your existing Draw calls open in it; it shows meshes, geometries and solution fields with clipping, deformation, vectors, fieldlines and isosurfaces, OCC face/edge picking, Plotly and matplotlib tabs, and probing by picking, and it can save and load its whole state. Because it is built from ngapp components, its viewers — mesh, function, geometry, plot — can be dropped into your own app or subclassed.

The talk covers the component model, styling and embedded 3D views, how apps are run and deployed, and how to reuse the GUI's pieces in your own apps.