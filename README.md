# Nucleosome Vector Analysis
A Python script designed to calculate the normal vectors of planar regions and the angles between them, while also generating a PyMOL script file (.pml) for visualization.

## Workflow
1. Visually inspect a multi-nucleosome structure and identify the chains corresponding to each histone octamer.

2. Determine the nucleotides located within 4 Å of the octamers and note their ranges.
For example, you can use the following commands in PyMOL to select the regions and list the nucleotides (assuming K and S are the DNA chains):
```
select oct1, chain A+B+C+D+E+F+G+H
select dna1, byres oct1 around 4 and chain K+S
iterate dna1 and n. P, print(chain, resn, resi)
```

3. Define the regions in a plain text file using the following format:
```
REGION: bottom
K 299 412
S 152 264
REGION: middle
K 432 544
S 10 131
REGION: top
K 153 278
S 272 409
```

4. Run the script in a terminal emulator.
```
nucleosomes.py test.pdb regions.txt
```
The script will output the normal vectors and centroids, along with a `test.pml` file.

5. Open the test.pml file in PyMOL.
This will display the structure and the normal vector for each region defined in the regions file, alongside labelling the angles.
