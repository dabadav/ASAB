# ASAB-CMAGE
## WORKFLOW 

 Get the VCF of the chrX and parse the interval matching the ACE2 gene [VCFtools] 

# Download all files in ftp directory 

wget -m ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/data_collections/1000G_2504_high_coverage/working/20201028_3202_phased/ 

# Download chromosome X 

wget ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/data_collections/1000G_2504_high_coverage/working/20201028_3202_phased/CCDG_14151_B01_GRM_WGS_2020-08-05_chrX.filtered.eagle2-phased.v2.vcf.gz 

 

# Extract specific regions of vcf containing ACE2 gene 

vcftools --vcf CCDG_14151_B01_GRM_WGS_2020-08-05_chrX.filtered.eagle2-phased.v2.vcf --chr chrX --from-bp 15494566 --to-bp 15607236 --recode 

 

# How to work with compressed file  

vcftools --gzvcf CCDG_14151_B01_GRM_WGS_2020-08-05_chrX.filtered.eagle2-phased.v2.vcf.gz --chr chrX --from-bp 15494566 --to-bp 15607236 –recode 

 

# Clean vcf file 

vcftools --vcf out.recode.vcf --remove-indels --recode --recode-INFO-all --out SNPsACE2_region 

 

# How many variants in the gene 

less SNPsACE2_region.recode.vcf | grep -c 'chrX' 

1375 



 

https://github.com/WeiYang-BAI/Impu-Reference-Panel-Reconstruction/blob/master/reference_panel_re-construction.py 


 
2. Compute the phylogeny tree (NJ – with Phylip) 
 
