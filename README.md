Pegamoid
========

Pegamoid is an orbital viewer especially suited for use with
[OpenMolcas](https://gitlab.com/Molcas/OpenMolcas). It can be used to view
orbitals and quickly select active spaces for use in CASSCF or RASSCF
calculations.

Screenshots
-----------

<img src="https://gitlab.com/Jellby/pegamoid/raw/master/screenshots/nonorthogonal.png" height=200 />
<img src="https://gitlab.com/Jellby/pegamoid/raw/master/screenshots/difference.png" height=200 />
<img src="https://gitlab.com/Jellby/pegamoid/raw/master/screenshots/gradient.png" height=200 />
<img src="https://gitlab.com/Jellby/pegamoid/raw/master/screenshots/labels.png" height=200 />
<img src="https://gitlab.com/Jellby/pegamoid/raw/master/screenshots/list.png" height=200 />

Features
--------

The following formats can be opened:

* HDF5 files, as generated by some (Open)Molcas modules like SCF or RASSCF, if compiled with HDF5 support.

* InpOrb files, generated by some (Open)Molcas modules like SCF or RASSCF, provided an HDF5 file for the same system was opened first.

* [Molden](http://www.cmbi.ru.nl/molden/) files.

* [Luscus](http://luscus.sourceforge.net/) files, generated by the GRID_IT module.

* Grid files (ASCII), generated by the GRID_IT module.

* [Cube](http://paulbourke.net/dataformats/cube/) files (formatted).

For HDF5, InpOrb and Molden files, orbitals are computed on the fly from the
basis set, and it is possible to change the sampling resolution and shape and
size of the sampled volume. Luscus, grid and cube files contain precomputed
volumetric data and only the existing data can be displayed.

Depending on availability in the input file, the following features and objects
are supported:

* Selection of orbital.

* Selection of spin.

* Selection of symmetry irrep.

* Natural average or state-specific orbitals.

* Electron density and Laplacian.

* Natural average or state-specific spin orbitals.

* Spin density.

* Natural difference orbitals.

* Difference, attachment and detachment density.

* Natural transition orbitals.

* Hole and particle density.

For any orbital or density, gradient lines can be computed and displayed
(particularly significant for the electron density). Densities can be computed
for reduced subsets of orbitals (for instance, only for the active orbitals),
and the user can write arbitrary notes for each orbital.

The value and opacity used to display isurfaces can be adjusted and the display
of the following elements can be toggled:

* Positive and negative parts of the isosurface.

* Nodal surfaces.

* Nuclei and bonds.

* Atom labels.

* Volume box.

Finally, the type of orbital (inactive, active...) can be changed and the
orbitals saved in the following formats usable in the (Open)Molcas programs:

* HDF5 format.

* InpOrb format.

or the current volumetric data or snapshot can be saved as:

* Cube format.

* PNG image.

Installation
------------

The recommended way to install Pegamoid is by using the [`pip` package
manager](https://packaging.python.org/tutorials/installing-packages/#use-pip-for-installing):

    pip install Pegamoid

(you may also want to add the flags `--upgrade` and/or `--user`).

There are other ways to get Pegamoid. One is cloning the git repository, e.g.

    git clone https://gitlab.com/Jellby/Pegamoid.git

Another way, since Pegamoid is contained in a single python script, is
downloading only the script file
[pegamoid.py](https://gitlab.com/Jellby/Pegamoid/raw/master/pegamoid.py?inline=false).

Once the program is fetched, it can be run directly or through a python
interpreter, no installation is needed, i.e.

    ./pegamoid.py

or

    python pegamoid.py

However, the script has some requirements (this should be taken care of by
`pip`, if you use it) that must be installed for it to work:

* Python 2 or python 3 (at least versions 2.7 and 3.4 have been tested).

* Qt with python bindings. PyQt 4, PyQt 5 and Pyside have been tested. It is
  recommended to install the python module qtpy (needed for Pyside).

* VTK with python bindings. Version 8.1.0 has been tested, earlier versions
  will most likely not work.

* The numpy and h5py python modules.

* Other python modules that may not be installed by default, it should be clear
  which ones, if any, are needed when trying to run Pegamoid.

Use with a remote connection
----------------------------

Production calculations are usually not run on the local machine, but on some
remote server like a supercomputer. To view/save/modify orbital files, it is
always possible to transfer the files between the local and remote machines. It
is, however, more convenient to run Pegamoid directly on the remote machine and
have the graphical interface display in the local machine. Unfortunately, there
are some difficulties that make this nontrivial.

First, the different requirements may not be installed in the remote system. A
possible solution is installing them for the user account with e.g.
``pip install --user``. In this case it will probably be easier to install qtpy
and Pyside instead of PyQt.

Then, the VTK visualization uses some advanced OpenGL features that may not be
available with all graphical drivers and it could be challenging to make it
work through a remote connection. We have had success running Pegamoid with
``vglrun`` inside a
[ThinLinc](https://www.cendio.com/thinlinc/what-is-thinlinc) session, or a VNC
session opened directly from an ssh connection. The specific needs and working
solution will probably depend on the hardware and software available in the
remote computer.
