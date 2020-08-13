Calculates the average length of transcripts belonging to each gene from a gtf/gff annotation file. Best to run it on a computer with many cores. It probably isn’t the fastest tool for this job. To use, ensure Rscript is installed on your system. You will also need to know the tags for gene id and transcript id in column 9 of the gtf file. Column 9 is the semicolon-delimited attributes column for each feature (e.g. exon, CDS, gene, etc.). Usually, “gene_id” and “transcript_id” are the tags. For example the attributes tags for genes and transcripts for an exon appear as:

gene_id “FBgn0052816”; gene_symbol “CG32816”; transcript_id “FBtr0070102”; transcript_symbol “CG32816-RA”;

For help type: ./compute_gene_transcripts_length.sh -h

Here is an example command:

./compute_gene_transcripts_length.sh -g gene_id -t transcript_id -c 8 -f annotation.gtf

This will take several hours to run and will output two files, a transcript length file and a mean transcript length file for each gene. Ensure that your gene lengths table has the same gene order as your gene expression table before instantiating a zigzag object.
