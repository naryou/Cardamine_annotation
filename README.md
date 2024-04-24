# Cardamine_annotation

*Narcis April 2024*

## TE annotation

* Run [RepeatModeler2](https://github.com/Dfam-consortium/RepeatModeler/tree/master) 

* Run [EDTA](https://github.com/oushujun/EDTA) to get a better classification of the repeats. It makes sense to talk to Thomas Wicker for TE libraries to be used.

* Run [RepeatMasker](https://www.repeatmasker.org/RepeatMasker/) to mask the genome for repeats (soft masked; i.e. putting repeat regions into lower case letters and all other regions into upper case letters)

## Gene annotation
* Align RNA-seq reads to the masked genome assembly using [HISAT2](http://daehwankimlab.github.io/hisat2/)

  Note: RNA-seq data from another population is fine

  * Convert the SAM file to BAM file using [samtools](https://github.com/samtools/)
  * Sort the BAM file
  * Split the sorted BAM file. For an explanation on the splitting step see this [link](https://www.biostars.org/p/348134/)  
     
* Run [Braker3](https://github.com/Gaius-Augustus/BRAKER). Braker runs both GeneMark-ET and AUGUSTUS

  * Prepare OrthoDB protein file: https://bioinf.uni-greifswald.de/bioinf/partitioned_odb11/ 
  * You can also prepare protein file of a close species, e.g. Arabidopsis thaliana and merge it with the OrthoDB file.

## UTR annotation
You can use [GUSHR](https://github.com/Gaius-Augustus/GUSHR) which employs [GeMoMa](http://www.jstacs.de/index.php/GeMoMa)

## Functional annotation

[EggNog](https://github.com/eggnogdb/eggnog-mapper/wiki/) and [TRAPID](http://bioinformatics.psb.ugent.be/trapid_02/) can be used.





