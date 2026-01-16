# Data Management Plan

## Types of data we generate:
- individual organismal measurements
- nutrient concentrations
- environmental data
- molecular metadata (DNA/RNA conc.)
- biological samples (tissues, molecules, slides)
- demographic & survey data
- sequencing
- images/videos

## General Plan
All raw data should be uploaded to the corresponding GitHub repo. NO raw data should be stored on the GW Lab Google Drive. Images/videos are stored on the [GW Lab Drive](https://drive.google.com/drive/folders/1LzfnaX87sDi6W1-xSfR6NYGwAgE8RS-7).

All project repos should contain a README with the following information *at minimum*:
- brief description of project/experiment
- table of contents/directory information
- links/locations to relevant external data (like images/videos on the Drive)
- links to associated analysis repos
- links to relevant protocols used to generate data (as needed/if applicable)

All metadata CSVs should have an original order column for sorting. If column names are not easily understandable, a README should be added for more descriptions (e.g. listing measurement units).

All generated samples that are being stored in the lab should be tracked in a CSV (freezer, box number, shelf, cabinet, etc.) and updated as needed (e.g. sample is extracted or depleted).


## Sequencing

#### NCBI Sequence Archive
Once sequences are received, they should be uploaded to the [NCBI SRA](https://www.ncbi.nlm.nih.gov/sra) (see [protocol](https://github.com/GWLab-UML/Protocols/blob/main/Computational/SRA-tutorial.md) on how to do this via command line).
#### Lab hard drive
Upload raw sequences to the lab hard drive in GW Lab with FileZilla

==protocol for FileZilla==

#### tar.zip on unity??


#### master spreadsheet
Update [SampleSeqInfo.csv](https://github.com/GWLab-UML/MegaMetaData/blob/main/SampleSeqInfo.csv) with metadata, sequencing information, file locations, and NCBI accession numbers.


## Project Repo Management 

### Day-to-Day
Committing early and often with active and descriptive voice. Push (at minimum) at the end of the day.

### Long-term
All GitHub repos used for analysis are required to be made public by submission of an associated manuscript or departure of the lab. Until then, repos can be private or public. Repos should be in an archival format (like [zenodo](https://zenodo.org/)) once the associated manuscript has been accepted for publication.

Project repos should contain a README with the following information *at minimum*:
- authors/collaborators
- brief description of the project
- table of contents/directory information
- link to broader project repo/metadata (if applicable)
- NCBI SRA accession number or link (if applicable)

Bash scripts and jobs should be run out of the /work directory, but scripts related to processing sequences should be copied into project repo.

Other suggestions for *good practice*:
- short description of the purpose of each code notebook
- plot descriptions with code notebook used to generate it


## Unity Workspaces
Best practices for utilizing Unity workspaces
#### /scratch
temporary space (30 days) with lots of storage (see [documentation](https://docs.unity.rc.umass.edu/documentation/managing-files/hpc-workspace/))
- downloading raw sequences
	>but not meant for long-term storage of raw seqs!
- QA/QC and trimming steps
- alignment (if generating large files)

#### /work
high performance storage space with 3-day snapshot
- storing bash scripts
- submitting jobs
- large environments

#### /project
storage space with 3-day snapshot - slower for running scripts
- storing genomes
- storing outputs and git backups (repos)
	- processing scripts have to be run out of work, but should be copied into project repo
