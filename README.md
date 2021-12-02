## diagnostics_vec: A diagnostics package for [MITgcm](https://github.com/MITgcm/MITgcm)

Authors: Michael Wood, Ian Fenty, April Shin

## Package Purpose and Motivation
The MITgcm model has one method for outputting model "diagnostics" for a particular experiment: dump the entire field. While entire model fields are desired for many experiements, this is not always the case. Here, we design a model package which is capable of outputting model diagnostics in a subset of the model domain e.g. along a vector (or "vec"). 

## Getting Started
The purpose of this repository is to provide a convenient way to merge new package files, verification experiments, and documentation into a fresh clone (and eventually a fork) of the main branch of MITgcm. To faciliate this merge, there are three convenient scripts provided in the [utils](https://github.com/mhwood/diagnostics_vec/tree/main/utils) directory. To start, clone this repository into a convenient drive on your machine. Then, `cd` to the utils directory and run the following code from the command line, passing the path to a (preferrably fresh) clone of the main branch of the MITgcm:
```
python3 copy_doc_files_to_MITgcm.py -m /path/to/MITgcm_fresh
python3 copy_pkg_files_to_MITgcm_.py -m /path/to/MITgcm_fresh
python3 copy_verification_files_to_MITgcm.py -m /path/to/MITgcm_fresh
```

## Repository Structure:
The main components to be included in the eventual pull request are staged in three directories as follows:
- doc: updates to the documentation for the [readthedocs](https://mitgcm.readthedocs.io/en/latest/) page
- pkg: the diagnostics_vec package files
- verification: experiments to be added to the verification directory of MITgcm to ensure the package is working as desired

Note that this repository has two additional directories which will not be included in the eventual pull request:
- example_configurations: a set of examples showing how the package works in a variety of configurations - jupyter notebooks are additionally provided to demonstrate the package use
- utils: functions that facilitate the development of this package and the eventual pull request, as described above

## Recommended Future Improvements to diagnostics_vec
1. Implement option to output data into a netCDF file, using the ``mnc`` package.
2. Add option to output a "snapshot" by providing frequecy as a negative number (following the convention established in the diagnostics package)
3. ~~Add option to use different averaging frequencies for each mask.~~ :white_check_mark:
4. ~~Add option to limit number of iterations stored in output files~~ :white_check_mark:

