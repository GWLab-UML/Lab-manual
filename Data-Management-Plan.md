# Data Management Plan

## Types of data we have:
- individual organismal measurements (length, width, area, health)
	- currently: CSV in project repo
	- ideas:
		- README should have column info if not clear from column name & hyperlink relevant protocols
		- always have an original order column for sorting
- nutrient concentrations
- environmental data
- molecular metadata (DNA/RNA conc.)
- samples
	- histology slides - track Y/N for histology, record location of finished slides
- demographic data (counts of individuals)
	- survey/population data
- sequencing
- images/videos - stay on google drive
	- in relevant project repo, README should have info on where to find the images
- protocols
- administrative - stay on google drive

all raw data should be uploaded to github

analyses are personal project repos - eventually become public and linked to corresponding project



## Sequencing

#### NCBI Sequence Archive
Once sequences are received, they should be uploaded to the [NCBI SRA](https://www.ncbi.nlm.nih.gov/sra) (see [protocol](https://github.com/GWLab-UML/Protocols/blob/main/Computational/SRA-tutorial.md) on how to do this via command line).
#### Lab hard drive
Upload raw sequences to the lab hard drive in GW Lab with FileZilla

==protocol for FileZilla==

#### tar.zip on unity??


#### master spreadsheet
Update [SampleSeqInfo.csv](https://github.com/GWLab-UML/MegaMetaData/blob/main/SampleSeqInfo.csv) with metadata, sequencing information, file locations, and NCBI accession numbers.

## Unity Workspaces
Best practices for utilizing Unity workspaces
#### /scratch
temporary space (30 days) with lots of storage (see [documentation](https://docs.unity.rc.umass.edu/documentation/managing-files/hpc-workspace/))
- download raw sequences
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



## Project Repo Management 

### Day-to-Day
Committing early and often with active and descriptive voice. Push (at minimum) at the end of the day.

### Long-term
All GitHub repos used for analysis are required to be made public by submission of an associated manuscript or departure of the lab. Until then, repos can be private or public. Repos should be in an archival format (like [zenodo](https://zenodo.org/)) once the associated manuscript has been accepted for publication.

Project repos should contain a README with the following information *at minimum*:
- authors/collaborators
- brief description of the project
- NCBI SRA accession number or link
- table of contents/directory information

Bash scripts and jobs should be run out of the /work directory, but scripts related to processing sequences should be copied into project repo.

Other suggestions for *good practice*:
- short description of the purpose of each code notebook
- plot descriptions with code notebook used to generate it