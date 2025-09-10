# CADD (Docking)
A short docking protocol for a protein

## Receptor and Ligand
The receptor is the TEM-1 beta-lactamase downloaded from [RCSB PDB](https://www.rcsb.org/structure/7U6Q). Additionally, here is the link to directly download the protein in the PDB format https://files.rcsb.org/download/7U6Q.pdb.

The ligand was taken from the PubChem database and downloaded in the SDF format.

## Conversion
The conversion of .sdf to .pdb file of the ligand was done using [UCSF Chimera](https://www.cgl.ucsf.edu/chimera/).

Additionally, the pdbqt files in the /Docking folder are converted using the **Autodock Software**, which helps in providing charges to the ligand, adding hydrogens, removing water, etc.
