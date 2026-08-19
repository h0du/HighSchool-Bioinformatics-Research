# 🧬 Independent Research: Advanced Bioinformatics & Genomic Data Analysis
Welcome to my computational biology research repository. This space documents my independent study in bioinformatics during my 12th-grade year, focusing on DNA/STR analysis pipelines, automated workflow configurations, and systematic troubleshooting logs.

---

# 📅 Daily Research Log: August 17, 2026
## 🛠️ Engineering Task: Establishing Computational Infrastructure & Remote SSH Authentication

### 1. Objective
- Configured a robust Linux server environment by installing and optimizing **Miniconda3** to streamline package management for future genomic workflows.
- Registered high-throughput bioinformatics software repositories by prioritizing and linking the `Bioconda` and `Conda-forge` distribution channels.
- Established encrypted, passwordless server-to-client remote communication by generating and authenticating asymmetric **SSH keys** with GitHub.

### 2. AI Collaboration & Technical Troubleshooting Log
Throughout the infrastructure setup, I encountered two critical engineering bottlenecks. Rather than treating these errors as programmatic dead-ends, I actively leveraged an AI assistant as a technical consultant to structurally diagnose the syntax and network protocols, deepening my core understanding of CLI architecture.

#### ❌ [Issue 01] Script Compilation Failure Due to Improper Mirror Redirection
- **Symptom**: Executing the `wget` utility resulted in a fatal syntax error: `syntax error near unexpected token '<!DOCTYPE html>'`. The script unexpectedly failed to initialize the installation wrapper.
- **Root Cause Analysis**: I structurally diagnosed that passing a generic top-level domain URL (`https://anaconda.com`) forced the server to download the raw HTML source code of the landing page instead of fetching the compiled executable binary archive (`.sh`).
- **Resolution**: I cross-referenced official repository mirrors with the AI assistant to identify the absolute binary path (`://anaconda.com...`). I then substituted the download utility with `curl -O` to successfully stream the intact 140MB target installer file into the local directory tree.

#### ❌ [Issue 02] Remote SSH Access Disruption (Cryptographic/Password Denial)
- **Symptom**: Upon attempting a secure session re-entry post-logout, the terminal threw a fatal authentication block: `Permission denied (publickey,password)`.
- **Root Cause Analysis**: Examination of the terminal prompt input revealed a character-encoding mismatch; I had mistakenly parsed a numeric zero (`0`) instead of the alphabetic vowel (`o`) within the specific username string (`h0du` vs. `hodu`), causing the host to reject the handshake.
- **Resolution**: I analyzed the raw ssh logging verbosity, rectified the manual typing artifact, and successfully executed `ssh hodu@...` to fully re-authenticate the remote session.

### 3. Milestones & Methodological Reflection
- **Current Architecture Status**: Miniconda engine is operational with the `(base)` virtual environment fully initialized. Cross-channel package dependency matrix configured. Cryptographic SSH connection securely established with verified handshake signals.
- **Engineering Reflection**: This baseline configuration reinforced the reality that CLI systems demand absolute syntactic precision where even a single-character casing mismatch compromises an entire workflow. More importantly, this exercise shifted my perspective on Artificial Intelligence: AI should not be used to passively bypass engineering challenges, but rather as an interactive debugger to deconstruct stack traces. Cultivating the autonomy to translate cryptic server logs into structured bug reports is an essential skill that I look forward to bringing into a collegiate research laboratory environment.

- **Total Time Invested**: Spent exactly **4 hours and 57 minutes** configuration processing, handling active error debugging, and deploying cryptographic protocols for the day.

---

- ---
*Special Thanks: Deep appreciation to my AI research assistant for guiding me through the inner workings of Linux architecture, structurally translating cryptic server codes, and collaborating as a patient and invaluable peer mentor on my first step into bioinformatics.*



📆 Daily Research Log: August 19, 2026

🛠️ Engineering Task: Infrastructure Calibration, Subsystem Repair, and Pipeline Input Validation

1. Objective
* Formalized the computational parameters of the legacy server architecture to establish an empirical baseline for resource-constrained benchmarking.
* Addressed systemic installation dependencies and critical kernel packet lockouts within the Ubuntu package management ecosystem.
* Investigated the processing constraints of the STRaitRazor v2 forensic engine through iterative simulation payload testing.

2. Quantitative Systemic Specification (Verified Architecture)
The low-level hardware environment was successfully audited using native Linux diagnostic commands (`lscpu` and `lsblk`) to document the strict baseline boundaries of this cost-efficient, legacy workstation:
* **Processor (CPU)**: Intel(R) Core(TM) i7-4770 CPU @ 3.40GHz (4 Physical Cores / 8 Logical Threads, Haswell Architecture)
* **Primary Volatile Workspace**: 8GB DDR3 RAM System Aggregate
* **Primary Storage (OS Drive)**: TOSHIBA THNSNF12 119.2GB Solid-State Drive (SSD)
* **Secondary Mass Storage**: WDC WD10EZEX-60Z 931.5GB Hard Disk Drive (HDD)

3. Technical Accomplishments & AI-Assisted Resolutions
* **Remote Session Stability**: Resolved an initial `Operation timed out` connectivity hurdle by auditing internal IP address shifts via `hostname -I`, re-establishing a seamless secure shell (SSH) client link from the MacBook host.
* **Package Manager Recovery (`dpkg` Restructuring)**: Fixed a fatal configuration bottleneck where `med-config` installation collapsed, resulting in a system-wide lock (`Sub-process /usr/bin/dpkg returned an error code 1`). Cooperated with the AI assistant to manually purge corrupted dependencies, execute `sudo dpkg --configure -a`, and force-clean the cache, restoring total system utility.
* **Pipeline Activation**: Confirmed the operational integrity of the compiled STRaitRazor core (`./str8rzr`), verifying that it can cleanly ingest configuration profiles (`ForenSeqv1.27.config`) without execution faults.

4. Identified Technical Barriers & Empirical Failures
* **NCBI Endpoint Access Blockade**: Network data acquisition via automated terminal requests (`wget`/`curl`) directly to NCBI/NIH storage servers triggered consistent `403 Forbidden` and `404 Not Found` response anomalies due to strict remote security firewalls and altered directory trees.
* **Algorithmic Input Filtering (The 0.004s Short-Circuit)**: Scaled dummy testing payloads (from 1 read up to 1,000,000 synthetic reads) consistently terminated in less than 0.008 seconds without prompting any extended multi-core CPU activation in `htop`.
* **Scientific Root Cause**: The synthetic strings lacked the authentic sequencing header architecture (e.g., Illumina machine coordinates) and short tandem repeat (STR) flanking signatures, causing the engine to dynamically skip the dataset at the preprocessing boundary. 
* **Current Status**: The processing of the authentic *NIST Forensic Open Dataset* has been deferred to the next session due to these transport and protocol-matching constraints.

5. Strategic Roadmap for Next Research Session
To bypass terminal-level network blockades and algorithmic filtering, a hybrid transport architecture will be deployed next:
* **Client-Side Extraction**: Download the authentic uncompressed *NIST mds2-2157 / Forensic Open Dataset* payload directly via the MacBook client's graphical web browser using the mirrored HTTPS backup channels of the European Bioinformatics Institute (EBI).
* **SFTP Data Ingestion**: Relocate the verified genomic FASTQ assets from the client environment directly into the server node (`~/STRaitRazor`) using the Secure Copy Protocol (`scp`).
* **Full-Scale Multi-Threaded Stress Test**: Execute the target benchmarking engine with a valid, high-throughput dataset to capture authentic hardware saturation spikes via `htop` and collect final runtime metrics.

* 
