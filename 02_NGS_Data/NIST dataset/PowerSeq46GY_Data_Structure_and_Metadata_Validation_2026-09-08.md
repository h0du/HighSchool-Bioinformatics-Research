
# PowerSeq 46GY Data Structure and Metadata Validation

## Dataset

* Dataset: NIST Forensic DNA Open Dataset
* Version: 1.4.0
* Assay: Promega PowerSeq 46GY
* DOI: 10.18434/M32157

## Confirmed Facts

### Directory Structure

The downloaded PowerSeq 46GY dataset contains:

* `PowerSeq46GY-MixturePlate`
* `PowerSeq46GY-SingleSource`
* `README_NGS_PS.txt`

The `PowerSeq46GY-MixturePlate` directory is approximately 22 GB.

### Filename Structure

According to the NIST README, MixturePlate filenames follow the structure:

`[kit]_[well]_[#contributors-mixture]_[ratio]_[input]_[sequencing run information]`

Example:

`PS_G1_3P-A_5-5-90_0.25_S73_L001_R2_001.fastq`

The README defines this example as:

* Kit: `PS`
* Plate well: `G1`
* Number of contributors: `3P`
* Mixture: `A`
* Ratio: `5%-5%-90%`
* DNA input: `0.25 ng`
* Sequencing sample number: `S73`
* Lane: `L001`
* Read: `R2`

### Contributor Metadata

The README explicitly confirms:

* `3P` = 3 contributors
* `4P` = 4 contributors
* `5P` = 5 contributors
* `1P-A` = a limited sensitivity series

Observed target mixture sample counts, counting one R1 file per paired-end sample:

* 3P: 48 samples
* 4P: 24 samples
* 5P: 18 samples
* Total 3P/4P/5P samples: 90

### Experimental Variables

The filename contains metadata fields for:

* plate well
* mixture code
* contributor ratio
* DNA input
* sequencing-run information

Repeated combinations of some conditions were observed in the MixturePlate filenames.

### Paired-End Structure

The README states that paired-end reads (`R1` and `R2`) are present for each sample.

### FASTQ Spot-Check

One R1 FASTQ file was manually inspected using the first eight lines.

The expected four-line FASTQ record structure was observed:

1. read identifier
2. nucleotide sequence
3. `+` separator
4. quality-score string

### Special Case: F10

The NIST README states that sample:

`F10_5P-B_1-1-1-48-49_1`

was resequenced because of a failure during the first sequencing round.

The README also states that this sample has higher coverage because it was multiplexed with fewer samples during resequencing.

## Interpretations

* The contributor-count labels (`3P`, `4P`, `5P`) will be retained as metadata for a later downstream NOC classification task.
* The repeated filename conditions may become relevant when later designing downstream analysis or machine-learning evaluation, but no analytical conclusion is being drawn at the current stage.
* The FASTQ spot-check supports that the inspected file has a normal basic FASTQ structure, but it does not establish the integrity of the full dataset.

## Unresolved

Some filenames contain a `D` suffix, for example:

* `1-1-98D`
* `1D-1D-98D`
* `3-32-65D`
* `3D-32D-65D`

The meaning of the `D` suffix has not been confirmed from the available README.

**Status: Unresolved**

No interpretation will be assigned until supported by official documentation or other reliable metadata.

## Not Yet Performed

* full FASTQ integrity validation
* STRait Razor processing of NIST PowerSeq FASTQ data
* STRait Razor output validation
* feature extraction
* NOC machine-learning training
* NOC model evaluation
