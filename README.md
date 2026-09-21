#Lecture 11: Programmatic Database Acess
## Date: Mon Sep 21 10:40:46 AM CEST 2026

# Create a directory for this exercise
mkdir -p ~/course/lecture11-databases
cd ~/course/lecture11-databases

# Neither git nor curl is on PATH by default on every Kebnekaise node -
# load both explicitly (they share the same GCCcore/14.3.0 toolchain)
module load GCCcore/14.3.0 git/2.50.1 cURL/8.14.1

# Initialise a Git repository
git init

# Create a README file
echo "# Lecture 11: Programmatic Database Access" > README.md
echo "## Date: $(date)" >> README.md
git add README.md
git commit -m "initial commit: lecture11 exercise setup"



## Data retrieved
- TP53_mRNA.fasta — Human TP53 mRNA (NM_000546.6) from NCBI RefSeq in FASTA format
- TP53_mRNA.gb   — Same record in GenBank format
- TP53_protein.fasta — Human TP53 protein (P04637) from UniProt Swiss-Prot in FASTA format
- TP53_protein.txt   — Full UniProt annotation record for P04637


## Key findings and questions answered:

##FastA file:
#Fetch RefSeq mRNA record for human TP53 (accession NM_000546.6) in FASTA format:
curl "https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nucleotide&id=NM_000546.6&rettype=fasta&retmode=text" > TP53_mRNA.fasta

# How many sequences are in the file?
grep -c ">" TP53_mRNA.fasta
1
# How many characters (bytes) is the file?
wc -c TP53_mRNA.fasta
2628 TP53_mRNA.fasta
# How many lines?
wc -l TP53_mRNA.fasta
38 TP53_mRNA.fasta

Questions to consider: What information is in the FASTA header line? What does the accession number format tell you about this record?
#Organism it came from, gene identity and that it's mRNA. NM_ prefix tells us It's refsec mRNA data.




##Genbank format:

Questions: What additional information does the GenBank format provide compared to FASTA? Can you find the gene name, organism, and a description of 
what this transcript encodes?
#Genbank innehåller också rå sekvensdata men med metadata och annotationer. Genen Tp53 är från homo sapiens och kodar för en tumorsupressorgen


##Uniprot format:

Questions: How many amino acids does human TP53 have? How does the UniProt FASTA header format differ from the NCBI FASTA header? What information is 
encoded in each field?
#According to uniprot, 393. The uniprot header has way more annotated information. sp = swiss prot , p04637 Uniprot acession, p53_human = uniprot 
#entry name, Cellular tumor antigen p53= protein name, OS= organism species, OX organism taxonomy identifier, GN= gene name, PE= protein existence, 
#SV= sequence version


Is this a Swiss-Prot (reviewed) or TrEMBL (unreviewed) entry? 
#Reviewed=Swiss


What GO terms are associated with TP53?
# multiple cc=cellular component


# What evidence codes are used?
     57 IDA
      8 IEA
     21 IMP
     17 IPI
      4 ISS

## Database versions/acess date:
-NCBI Entrez acessed $(date)
-UniProt acessed: $(date)



