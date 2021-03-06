---
title: 'PyVista: 3D plotting and mesh analysis through a streamlined interface for the Visualization Toolkit (VTK)'
tags:
  - Python
  - visualization
  - 3D
authors:
  - name: C. Bane Sullivan
    orcid: 0000-0001-8628-4566
    affiliation: 1
  - name: Alexander A. Kaszynski
    orcid: 0000-0002-8232-7212
    affiliation: 2
affiliations:
 - name: Department of Geophysics, Colorado School of Mines, Golden, CO, USA
   index: 1
 - name: Universal Technology Corporation, Dayton, OH, USA
   index: 2

date: 10 February 2019
bibliography: paper.bib
---

# Summary

The availability of software for 3D visualization in Python is limited to
libraries that are either not capable of handling large, spatially referenced
datasets or have inherently complex application programming interfaces (APIs).
One of these software libraries is the Visualization Toolkit (VTK) [@vtkbook];
a powerful scientific visualization software library, and with Python bindings,
it combines the speed of C++ with the rapid prototyping of Python.
Despite this, VTK code programmed in Python using the base VTK python package
is unnecessarily complicated as its API merely binds existing C++ calls.
The PyVista Python package provides a concise, well-documented interface
exposing VTK’s powerful visualization backend; enabling researchers to
rapidly explore large datasets, communicate their spatial findings, and
facilitate reproducibility. PyVista further seeks to simplify standard mesh
creation and plotting routines without compromising on the speed of the C++
VTK backend. Figure 1 demonstrates an integrated scene of geospatial data
generated by PyVista; to learn more about how this visualization was created,
please visit [PVGeo's FORGE project website](http://forge.pvgeo.org).


![A visually integrated scene of geospatial data (FORGE Geothermal Site).
This rendering includes a digital land surface with overlain satellite
imagery and geologic map, a subsurface temperature model, scattered points
of the sampled temperature values, geophysical well logging data, GIS site
boundary, and interpreted faulting surfaces.](./images/forge-iso.png)


Plotting VTK datasets using only the VTK Python package or a similar
visualization library is often an ambitious programming endeavor.
Reading a VTK supported file and plotting it requires a user to write a
complicated sequence of routines to render the data object while
having to remember which VTK classes to use for file reading and dataset mapping.
An example can be found in [this creative commons VTK example](https://vtk.org/Wiki/VTK/Examples/Python/STLReader).
PyVista includes plotting routines that are intended to be intuitive and
highly controllable with `matplotlib` [@matplotlib] similar syntax and keyword
arguments. These plotting routines are defined to make the process of
visualizing spatially referenced data straightforward and easily implemented
by novice programmers; streamlining the process for creating integrated scenes
like that shown in Figure 1.


VTK implements an object-oriented approach to 3D visualization [@vtkbook],
and PyVista adhere's to that underlying structure to provide an API that
expands on VTK's data types. These expanded, wrapped types hold methods and
attributes for quickly accessing scalar arrays, inspecting properties of
the dataset, or using filtering algorithms to transform datasets.
PyVista wrapped objects have a suite of common filters ready for immediate
use directly on the objects. These filters are commonly used algorithms in the
VTK library that have been made more accessible by binding a method to control
that algorithm directly onto all PyVista datasets, providing a shared set of
functionality. Through the use of these bound filtering methods, powerful VTK
algorithms can be leveraged and controlled via keyword arguments designed to
be intuitive for novice users.
Figure 2 show examples of standard filtering algorithms.


![Examples of common filtering algorithms: A) threshold volume
extraction by scalar array, B) iso-contouring by scalar array, C) orthogonal
slicing through volume, and D) geometric glyphing at mesh nodes and scaled by
a scalar array.](./images/filters.png)


At its core, PyVista is a pure Python helper module for VTK
that interfaces back to VTK data objects through NumPy [@numpy]
and direct array access adhering to VTK's object-oriented approach to
3D visualization [@vtkbook].
The PyVista Python package provides an accessible and intuitive interface back
to the VTK library to facilitate rapid prototyping, analysis, and visual
integration of spatially referenced datasets.

## Mentions

PyVista is used extensively by the Air Force Research Labs (AFRL) for
data visualization and plotting in research articles including
figures visualizing 3D tessellated models generated from structured
light optical scanner and results from finite element analysis.
AFRL publications leveraging PyVista for 3D visualization include:
[@Gillaugh2017], [@Brown2018], [@Brown2018_pro], [@Beck2018_subspace],
[@Kaszynski2018], [@Gillaugh2018_art], [@Gillaugh2019]

[PVGeo](https://github.com/OpenGeoVis/PVGeo) is Python package of VTK-based
algorithms to analyze geoscientific data and models. PyVista is used to make
the inputs and outputs of PVGeo's algorithms more accessible and to streamline
the process of visualizing geoscientific data.


## References
