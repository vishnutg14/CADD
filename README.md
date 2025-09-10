# CADD (Docking Protocol)

A streamlined **Computer-Aided Drug Design (CADD)** workflow for docking **Penicillin G** against **TEM-1 β-lactamase** using **AutoDock Vina**.  
This repository provides the receptor, ligand, prepared docking files, and example outputs to reproduce or extend the docking experiment.

---

## Overview
This protocol demonstrates:
- Preparation of **receptor** and **ligand** structures.  
- File format conversions (SDF → PDB → PDBQT).  
- Running **AutoDock Vina** with a custom configuration.  
- Analyzing docking outputs: poses, binding affinities, and RMSD values.  

---

## Receptor and Ligand
- **Receptor**: [TEM-1 β-lactamase (PDB ID: 7U6Q)](https://www.rcsb.org/structure/7U6Q)  
  - Direct download: [7U6Q.pdb](https://files.rcsb.org/download/7U6Q.pdb)  

- **Ligand**: [Penicillin G (PubChem)](https://pubchem.ncbi.nlm.nih.gov/compound/5904)
  - Downloaded in **SDF** format.  
  - Converted to **PDB** using [UCSF Chimera](https://www.cgl.ucsf.edu/chimera/).  

---

## File Preparation
- **Ligand & Receptor** converted into **PDBQT** format using **AutoDock Tools**:  
  - Add hydrogens  
  - Assign charges  
  - Remove crystallographic water molecules  
- Docking was executed with **AutoDock Vina**.  

---

## Repository Structure
```
📦 CADD
 ┣ 📂 Docking/
 ┃ ┣ 7U6Q.pdbqt           # Prepared receptor
 ┃ ┣ 7u6q.cif             # Original mmCIF file
 ┃ ┣ config.txt           # Docking parameters (grid box, exhaustiveness, etc.)
 ┃ ┣ ligand.pdb           # Converted ligand via Chimera
 ┃ ┣ ligand.pdbqt         # Prepared ligand
 ┃ ┣ ligand.sdf           # Downloaded ligand
 ┃ ┣ log.txt              # Binding affinities & RMSD values
 ┃ ┣ output.pdbqt         # Output file in pdbqt format
 ┃ ┣ protein.pdb
 ┗ README.md
```

---

## Key Outputs
- **`output.pdbqt`** – Docked structure containing the top-ranked poses.  
- **`log.txt`** – Binding affinities (kcal/mol), RMSD values, and docking scores for the best 9 modes.  

---

## Running the Docking
1. Prepare receptor and ligand in **PDBQT** format.  
2. Edit `config.txt` with your desired parameters:  
   ```txt
   receptor = receptor.pdbqt
   ligand = ligand.pdbqt
   center_x = ...
   center_y = ...
   center_z = ...
   size_x = ...
   size_y = ...
   size_z = ...
   exhaustiveness = 8
   ```
3. Run AutoDock Vina:
   ```bash
   vina --config config.txt --out output.pdbqt --log log.txt
   ```

---

## References
- Trott, O., & Olson, A. J. (2010). *AutoDock Vina: improving the speed and accuracy of docking with a new scoring function, efficient optimization, and multithreading.* J Comput Chem, 31(2), 455–461.  
- UCSF Chimera: [https://www.cgl.ucsf.edu/chimera/](https://www.cgl.ucsf.edu/chimera/)  
- RCSB PDB: [https://www.rcsb.org](https://www.rcsb.org)  

---

## Use Cases
- Educational demonstration of **ligand–protein docking**.  
- Template for **custom docking workflows**.  
- Baseline protocol for **antibiotic resistance studies** involving β-lactamase.  
