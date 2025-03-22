# nucleosome-analysis
A Python script to calculate normal vectors of planar regions and angles between them, and generate a PyMOL script file (.pml) for visualization


## Work flow

1. visual inspection of a multi-nucleosome structure, identify the chains of each histone octomer.
2. identify the nucleotides that are within 4 A of the octomers and show note down the range
3. define the regions in a plain text file in the following format:
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
4. run the script in a terminal emulator
```
nucleosomes.py test.pdb regions.txt
```
This script shall generate an output of the normal vectors and centroids, and also a `test.pml` file.
5. Load the `test.pml` file in PyMOL.
It shall display the structure and the normal vector of each region defined in the regions file.
