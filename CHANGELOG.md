**2.4.2** (2019-09-12)

Bug fix:
* Fix writing of HDF5
* Write natural UHF orbitals too (if available)

**2.4.1** (2019-09-06)

Bug fixes:
* Fix reading color settings if not present in configuration file
* Fix transparency in PNG screenshots (in some Qt versions)
* Read Molden files with missing tags

**2.4** (2019-08-30)

New features:
* Display atoms with no basis functions (e.g. MM) as transparent balls and exclude them from box
* Options to fit and align box with molecule, manually or automatically on loading
* Improve Molden file reading
* Support two filenames in command line (useful for InpOrb files)

**2.3** (2019-07-25)

New features:
* Save and restore settings and window size/position
* Collapsible and detachable options panel
* Easier scratch configuration
* Allow overwriting current HDF5 file
* Add Fresnel-like transparency and presets

**2.2.2** (2019-05-25)

Bug fix:
* Keep grid fixed after computing Laplacian

**2.2.1** (2019-05-13)

Bug fix:
* Workaround for display issue on some PyQt5 systems

**2.2** (2019-04-23)

New features:
* Color/texture editor and presets
* Show box parameters for grid files
* Allow more control on scratch usage
* Allow interrupting long computations

**2.1.1** (2019-04-13)

Bug fix:
* Numpy compatibility improvement

**2.1** (2019-03-01)

New features:
* Support contaminant functions
* Balls & sticks representation

**2.0.2** (2019-01-21)

Bug fix:
* Correctly reset orbital type after changing it

**2.0.1** (2018-10-30)

Bug fix:
* Corrected electron density

**2.0** (2018-09-12)
* Rewritten to use Qt and VTK directly
* First version on PyPI (installable through `pip`)

New features:
* Density selection (state, difference, transition)
* Root selection
* Support UHF natural orbitals
* Numerical Laplacian
* Support for non-orthogonal grids
* Display atom labels
* Isosurface opacity
* Save image as PNG

**1.0** (2018-01-03)
* Initial public version, using Mayavi and TVTK
* Not available trough `pip`