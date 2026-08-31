# NIST Forensic DNA Dataset Acquisition Troubleshooting

Date: 2026-08-31
Status: Exploratory Workflow

## Objective

An initial attempt was made to obtain the NIST Forensic DNA Open Dataset for subsequent forensic STR analysis.

The purpose was to establish a reliable dataset acquisition and validation workflow before beginning downstream analysis.

## NIST Dataset

The NIST Forensic DNA Open Dataset contains both single-source and mixture samples and includes CE-STR and NGS assay data.

The repository currently lists the following NGS datasets:

- Promega PowerSeq 46GY
- Promega PowerSeq CRM Nested System
- Thermo Fisher Precision ID GlobalFiler NGS STR Panel v2
- Verogen ForenSeq DNA Signature Prep Kit

The specific dataset for the main experiment has not yet been finalized.

## Initial Download Attempt

An initial download was attempted using wget on the Ubuntu server.

The resulting file was:

nist_sample_R1.fastq.gz

Although the filename suggested a compressed FASTQ file, the file was validated before use.

### File Type Check

Command:

file nist_sample_R1.fastq.gz

Result:

HTML document, ASCII text, with very long lines

### Content Inspection

Command:

head -c 500 nist_sample_R1.fastq.gz

The output began with:

<!doctype html><html ...

This indicated that the file contained HTML content rather than FASTQ sequence data.

### GZIP Validation

Command:

gzip -t nist_sample_R1.fastq.gz

Result:

gzip: nist_sample_R1.fastq.gz: not in gzip format

### Conclusion

The downloaded file was confirmed to be an HTML response rather than a valid gzip-compressed FASTQ file.

The file was excluded from downstream analysis.

## Browser-Based Download Attempts

The NIST web interface was subsequently tested using:

- Google Chrome
- Mozilla Firefox
- Direct file download
- NIST Data Cart

The Data Cart download eventually resulted in an HTTP 524 error.

Direct file download also failed in the current environment.

## Cross-Environment Observation

A previous download of the NIST dataset had been successfully completed on a computer located outside the current research environment.

Therefore, the current failure was not interpreted as evidence that the NIST dataset itself was unavailable.

The exact cause of the current download failure remains undetermined.

## Decision

Repeated download attempts in the current environment were stopped.

The current plan is to obtain the validated dataset from the previously successful external environment and transfer it to the Ubuntu research server.

All files will be validated before downstream analysis.

## Planned Validation Workflow

NIST Dataset
    ↓
Download
    ↓
File type validation
    ↓
Integrity validation
    ↓
Archive validation
    ↓
FASTQ validation
    ↓
Metadata inspection
    ↓
Sample / mixture identification
    ↓
STRaitRazor analysis

## Research Relevance

This exploratory process illustrates an important aspect of the resource-constrained workflow.

Reducing hardware requirements can introduce additional technical barriers, particularly when using Linux-based scientific computing environments.

The broader research framework is:

Resource Constraints
        ↓
Legacy Hardware
        ↓
Linux Scientific Environment
        ↓
Technical Expertise Barrier
        ↓
AI-Assisted Troubleshooting
        ↓
Workflow Development
        ↓
Accessible Scientific Computing

The dataset acquisition problem is recorded as part of the exploratory troubleshooting process.

## Current Status

### Completed

- NIST dataset identified
- Repository-level dataset structure examined
- Ubuntu download attempted
- Invalid FASTQ file identified
- File format independently validated
- GZIP validation performed
- Browser download attempted
- Data Cart download attempted
- Cross-environment difference identified

### Next

- Obtain validated NIST dataset
- Transfer dataset to Ubuntu server
- Examine archive structure
- Identify FASTQ files
- Study FASTQ structure
- Identify sample and mixture information
- Determine available ground-truth information
- Begin STRaitRazor analysis
