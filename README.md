# BacMet: Antibacterial Biocide and Metal Resistance Genes Database

This repository is provide a database of DNA sequences of BacMet for abricate and other DNA based gene detection software commonly used in the microbial bioinformatics community.

# Method
All plasmids from the MOB-suite v. 3.0.0 database were annotated using prokka v.14.5 "--compliant".
The AA sequences were used as queries against the bacmet  protein queries with a minimum ident of 90% and coverage.
The ids of the proteins were then mapped back to the DNA sequences and those were dereplicated using CD-HIT-EST at 95% coverage and ident of the smallest sequence

#How to add to abricate
copy the specific database version to the abricate db folder for your evironment
```
cp -r database/confirmed_resistance_genes/2018-03-11-version-2/bacmet/ /path/to/abricate/db     
abricate --setupdb
```

#Citation
If you use the database here please cite BacMet as they are the ones who developed the database

Pal, C., Bengtsson-Palme, J., Rensing, C., Kristiansson, E., Larsson, DGJ. (2014) BacMet: antibacterial biocide and metal resistance genes database, Nucleic Acids Research, 42, D737-D743. doi: 10.1093/nar/gkt1252

**Outputs:**

```
OutputFolderName
├── database [Tree Mode Only]
	├── {type}
		├── {version}
			├── bacmet.fasta [abricate formatted fasta file]
			└── bacmet.txt   [TSV data of :uid,bacmet_id,gene_name,protein_id,taxon,location,resistance,dna_seq,aa_seq]
```