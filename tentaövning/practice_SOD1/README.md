##Retrieved NCBI entrez human SOD1 gene data in fasta format 2026-09-21 
https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nucleotide&id=NM_000454.5&rettype=fasta&retmode=text" > SOD1_mRNA.fasta


#Hur många sekvenser finns i filen?
1

#Hur många rader innehåller filen?
15
#Visa FASTA-headern.
NM_000454.5 Homo sapiens superoxide dismutase 1 (SOD1), mRNA


##Retrieved NCBI entrez gumaN SOD1 GENE data in GenBank format
(21/09/2026)
curl "https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nucleotide&id=NM_000454.5&rettype=fasta&retmode=text" > SOD1_mRNA.gb

#DEFINITION
#SOURCE
#ORGANISM
#(Using grep)

NM_000454.5 Homo sapiens superoxide dismutase 1 (SOD1), mRNA

##Retrieved P00441 in FastA format using Uniprot REST api

curl "https://rest.uniprot.org/uniprotkb/P00441.fasta" \
> SOD1_protein.fasta

#Hur många aminosyror? 
154



##Retrieved the full UniProt entry 
curl "https://rest.uniprot.org/uniprotkb/P00441.txt" > SOD1_protein.txt
(21/09/2026)



# Reviewed eller unreviewed 10 first go annotations which are C F or P?
Reviewed (Swissprot), CC terms only
DR   GO; GO:1904115; C:axon cytoplasm; IEA:GOC.
DR   GO; GO:0005737; C:cytoplasm; IDA:UniProtKB.
DR   GO; GO:0031410; C:cytoplasmic vesicle; IDA:UniProtKB.
DR   GO; GO:0005829; C:cytosol; IDA:UniProtKB.
DR   GO; GO:0032839; C:dendrite cytoplasm; IDA:UniProtKB.
DR   GO; GO:0031045; C:dense core granule; IEA:Ensembl.
DR   GO; GO:0070062; C:extracellular exosome; HDA:UniProtKB.
DR   GO; GO:0005576; C:extracellular region; IDA:UniProtKB.
DR   GO; GO:0005764; C:lysosome; IEA:Ensembl.





