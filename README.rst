.. image:: https://img.shields.io/badge/dmtn--140-lsst.io-brightgreen.svg
   :target: https://dmtn-140.lsst.io
.. image:: https://github.com/lsst-dm/DMTN-140/workflows/CI/badge.svg
   :target: https://github.com/lsst-dm/DMTN-140/actions/

#############################################################################
Documentation automation for the Verification and Validation of LSST software
#############################################################################

DMTN-140
========

LSST Data Management (DM) is responsible for creating the software, services, and systems that will be used to produce LSST's science-ready data products. The software, currently under development is heterogeneous, comprising both C++ and Python components, and is designed to facilitate both the processing of LSST images and to enable value-added contributions from the broader scientific community. Verification and validation of these software products, services, and systems is an essential yet time-consuming task. In this paper, we present the tooling and procedures used by the LSST project for a systematic verification and validation documentation approach. By adopting a systematic approach, we guarantee full traceability to system requirements, integration with the project’s System Engineering model, and substantially reduce the time required for the whole process.

Links
=====

- Live drafts: https://dmtn-140.lsst.io
- GitHub: https://github.com/lsst-dm/dmtn-140

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-dm/dmtn-140

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the `acronyms.tex` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
