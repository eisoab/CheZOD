# CheZOD
Script to compute residue-specific protein (dis)order from NMR chemical shifts

python command-line application

usage: python_exe chezod1_0.py bmrid [-p] > logfile &

python must be version 2

requires: numpy, scipy, pylab and pyqt

## Arguments for chezod:

bmrid specifies id for either (i) published BMRB id or (ii) a local provided NMR-STAR file id (version 2.1).

   (i) The data will be downloaded automatically from the corresponding ftp site for the specified bmrid.

   (ii) An NMR-STAR file named bmr<bmrid>.str (v2.1) must be placed in the running directory. In the py3 version also the full filename bmr<bmrid>.str is allowed as argument 
   
The NMR-STAR file:
- must contain chemical shifts (SCSs) and specify: “_Mol_residue_sequence", "assigned_chemical_shifts" and sample_conditions loop.
- there needs to be an empty line between the last line of the shift list and following line with 'stop_' ( e.g. not present in bmr*.str output from cyana. )

## Output files:

Output text files are generated with SCSs, “shiftsbmrid.txt”, and Z-scores “zscoresbmrid.txt”.

Z-score output has the following columns: residue name, residue number, and Z-score

shift file has: residue number, residue type, atom type, assigned chemical shift, pentapeptide context, and SCS. 

A plot windwow opens with Z-score profile (change flag "-p" to "-n" to omit plot. In this case pylab and pyqt are not required).
