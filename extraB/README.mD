# Search ENA for RNA-seq datasets from Populus tremula
curl "https://www.ebi.ac.uk/ena/portal/api/search?query=tax_eq(113636)%20AND%20library_strategy=%22RNA-Seq%22&result=read_study&fields=study_accession,study_title,scientific_name&format=tsv&limit=5" > populus_rnaseq.tsv


#Acessed 2026-09-21


cat populus_rnaseq.tsv


#Question: What does the query structure tell you about how the ENA API works? How might you modify this query to search for a different organism?



ENA returns one row per sequencing run, where each run has a unique run accession and can belong to the same study. To search for another organism, 
change the taxon specified in tax_eq in the URL.
