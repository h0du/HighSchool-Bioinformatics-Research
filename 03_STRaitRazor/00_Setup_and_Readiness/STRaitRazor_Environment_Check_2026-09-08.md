# STRait Razor Environment Check

## Purpose

This check was performed before running STRait Razor on the NIST Promega PowerSeq 46GY dataset.

No NIST PowerSeq FASTQ file was processed during this step.

## Confirmed Facts

### STRait Razor Location

The STRait Razor directory was located at:

`/home/hodu/STRaitRazor`

The executable exists at:

`/home/hodu/STRaitRazor/str8rzr`

The executable was not returned by:

`command -v STRaitRazor`

`command -v straitrazor`

or

`command -v straitrazor.py`

### Conda Environment

The active Conda environment was:

`base`

No separate STRait Razor Conda environment was listed.

### PowerSeq Configuration

The following PowerSeq-specific configuration file exists:

`/home/hodu/STRaitRazor/PowerSeqv2.31.config`

### Documented Command Syntax

The local STRait Razor README documents the basic command syntax as:

`str8rzr -c configFile fastqfile > allsequences.txt`

The README also provides a multithreaded example:

`str8rzr -p 8 -c configFile fastqfile > allsequences.txt`

### Documented Software Behavior

According to the local STRait Razor README:

* STRait Razor reports apparent alleles.
* The current implementation does not directly call genotypes.
* Reported alleles may include stutter alleles.
* STRait Razor uses a configuration file that must be appropriate for the sequencing chemistry.

## Interpretations

* The failure of `command -v` to return the executable indicates that the STRait Razor binary is not currently discoverable under the tested command names through the active shell PATH.
* Because `PowerSeqv2.31.config` exists in the STRait Razor directory, it is a candidate configuration file for the upcoming PowerSeq pilot analysis.
* Its actual suitability for the NIST PowerSeq 46GY FASTQ data has not yet been experimentally confirmed in this workflow.

## Unresolved

* Whether the current `str8rzr` executable runs successfully on the NIST PowerSeq 46GY data.
* Whether `PowerSeqv2.31.config` produces valid and interpretable output for this specific dataset.
* The exact output fields and structure that will be produced.
* Which output variables can later be used for feature extraction.

## Not Yet Performed

* STRait Razor pilot on an actual NIST PowerSeq FASTQ file
* runtime measurement on the PowerSeq pilot
* peak-memory measurement on the PowerSeq pilot
* output-format validation
* full-dataset processing
* feature extraction
* NOC classification
