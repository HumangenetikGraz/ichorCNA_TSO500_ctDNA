# TSO500offtarget_ichorCNA
Pipeline to compute SCNAs through ichorCNA using both off-target and on-target reads on output BAM files of TSO500 ctDNA analysis pipeline.
Original ichorCNA pipeline adapted at the Institute of Human Genetics, Medical University of Graz Austria.

## Contributors
 - Original ichorCNA work by Gavin Ha (Victor Adalsteinsson Lab)
 - Adapted initially by Isaac Lazzeri 
 - Adapted further for off-target read-based ichorCNA analysis by Raul Alejandro Mejia Pedroza 
 - Adapted for parallel processing of samples using multiprocessing for duplicate marking on a SLURM HPC environment by Benjamin Gernot Spiegl 
 - Maintained and optimized further by Matvii Mykhailichenko

## Requirements
UNIX OS with a **SLURM job management system** plus appropriate RAM and disk space.
If you don't have a SLURM job scheduling system inplace, you must comment out line 94 in `TSO500_ichorCNA_from_offtarget_reads_PARALLEL.sh` and uncomment line 95.

## Getting started
1) Set up the repo. Install ichorCNA from the official maintainer:
https://github.com/broadinstitute/ichorCNAThe path to the ichorCNA folder must be provided via `--ichorpath` to the driver script 'drv_TSO500_offtarget_ichorCNA_parallel.sh'.
2) create the 'TSO500ichorCNA' conda environment from the YAL file `conda/env.yaml`
3) activate the environment: conda activate TSO500ichorCNA
4) run the pipeline through the driver script `drv_TSO500_offtarget_ichorCNA_parallel.sh`

## Usage
The only other parameter aside of `--ichorpath` that needs to be provided is `--indir`, the path to the directory containing the indexed output BAM files from Illumina's ichorCNA ctDNA analysis pipeline.

## License
Artificial Intelligence Restrictions for Software (AIR-S)

## Project status
In production.
Please report issues to the repo.
