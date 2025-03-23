
# Klebsiella pneumoniae SNP Calling & Drug Resistance Annotation Pipeline

This pipeline is a comprehensive Bash script that automates quality control, variant calling, and drug resistance gene annotation for *Klebsiella pneumoniae* whole-genome sequencing data. It leverages tools such as **FastQC**, **MultiQC**, and **Snippy** to perform SNP calling and identify mutations associated with antibiotic resistance.

---

## Features

- Performs **quality checks** using FastQC
- Generates **combined quality reports** using MultiQC
- Calls **SNPs** using Snippy with a reference genome
- Detects and annotates **drug resistance mutations**
- Outputs **drug-specific resistance summaries** per sample

---

## Input Requirements

1. A `list.txt` file with one sample name per line (without file extensions).
2. Paired-end FASTQ files for each sample named as:
   - `sample_1.fastq.gz`
   - `sample_2.fastq.gz`
3. A GenBank reference file for *Klebsiella pneumoniae* (update the path in the script).

---

## How to Run

1. Make the script executable:
```bash
chmod +x klebsiella_pipeline.sh
```

2. Run the script from within your working directory:
```bash
./klebsiella_pipeline.sh
```

Ensure the script is located in the same directory as your FASTQ files and `list.txt`.

---

## Output Files

For each sample, the script generates:

- `sample.snps/` directory containing SNP calling output
- `sample.Drug-Resistance-Details.txt`: Detected resistance mutations
- Drug-specific summaries such as:
  - `sample.Aminoglycoside.Resistance.txt`
  - `sample.Beta-lactam.Resistance.txt`
  - `sample.Fluoroquinolone.Resistance.txt`, etc.

Empty files are automatically removed to declutter the output.

---

## Resistance Genes Detected

| Drug Class       | Genes Detected                           |
|------------------|------------------------------------------|
| Aminoglycosides  | `aacA4`, `rmtC`                          |
| Beta-lactams     | `bla`                                    |
| Chloramphenicol  | `ramR`                                   |
| Fluoroquinolones | `ramR`, `oqxA`, `oqxB`, `gyrA`, `parC`   |
| Fosfomycin       | `fosA`                                   |
| Polymyxins       | `mgrB`                                   |
| Sulfonamides     | `sul1`                                   |
| Tetracyclines    | `tet`                                    |
| Macrolides       | `mph`                                    |

---

## Quote to Remember

> **"Bioinformatics is not something you are taught, it’s a way of life."**

---


📧 Email: ...@gmail.com

---

## License

This script is provided under the **MIT License**.
