# Scripts for Part 1: Data Readiness

This folder holds scripts to help with Part 1 of the KnowHax 2025 [SPOKE For Space Health Challenge](https://docs.google.com/document/d/1nzzrIDcLS8-L2yQ5dBrkcIHtrjjQbVk8).

--- 

<br>

## Extract OSD metadata for pairwise comparisons

### Description

The `save_metadata.py` python script is designed to extract sample names and experimental factor values from studies hosted on the [NASA Open Science Data Repository](https://osdr.nasa.gov/bio/repo), and create files to specify sample groups and all pairwise comparisons.

<br> 

### Dependencies

[Python](https://www.python.org/) is required to run the script.

<br> 

### Download script

```bash
curl -LO https://raw.githubusercontent.com/asaravia-butler/KnowHax2025_NASA-SPOKE/refs/heads/main/Part1_Data_Readiness_Scripts/save_metadata.py
```

<br> 

### Usage

```bash
python save_metadata.py OSD-ACCESSION
```

<br> 

### Output

This script will output two CSV files, OSD-ACCESSION_SampleTable.csv and OSD-ACCESSION_contrasts.csv.

<br>

**OSD-ACCESSION_SampleTable.csv:** 
Table containing two columns, "Sample Name" and "Treatment Group", where the values in the "Sample Name" column correspond to the sample name for each sample in the OSD-ACCESSION dataset and the values in the "Treatment Group" column are the respective treatment group for each sample.
> *Note: Treatment groups are made by combining the values in each "Factor Value" column with an '&' symbol for each sample in the OSD-ACCESSION sample table.*
> *This can be used to identify which group each sample belongs to.* 

<br> 

**OSD-ACCESSION_contrasts.csv:** 
Table containing a column for each possible pairwise group comparison for the selected OSD-ACCESSION. Rows 1 and 2 under each column contain the treatment groups being compared.
> *Note: This can be used to identify all pairwise comparisons that should be performed in Part 1 of the KnowHax 2025 SPOKE For Space Health Challenge.*

<br> 

### Example using [OSD-295](https://osdr.nasa.gov/bio/repo/data/studies/OSD-295)

```bash
python save_metadata.py OSD-295
```

See the [OSD-295_example_outputs](OSD-295_example_outputs) folder to view the output CSV files for the example command above.




