# Cardamine_annotation

*Narcis April 2024*

## TE annotation

* Run [EDTA](https://github.com/oushujun/EDTA) which uses [RepeatModeler2](https://github.com/Dfam-consortium/RepeatModeler/tree/master) too. It makes sense to talk to Thomas Wicker for TE libraries to be used (it's optional).

* Run [RepeatMasker](https://www.repeatmasker.org/RepeatMasker/) to mask the genome for repeats (soft masked; i.e. putting repeat regions into lower case letters and all other regions into upper case letters)
> [!NOTE]
> EDTA runs RepeatMasker too but there were some problems and I re-ran it.

## Gene annotation
* Align RNA-seq reads to the masked genome assembly using [HISAT2](http://daehwankimlab.github.io/hisat2/)

> [!NOTE]
> RNA-seq data from another population is fine

  * Convert the SAM file to BAM file using [samtools](https://github.com/samtools/)
  * Sort the BAM file
     
* Run [Braker3](https://github.com/Gaius-Augustus/BRAKER). Braker runs both GeneMark-ET and AUGUSTUS

  * Prepare OrthoDB protein file: https://bioinf.uni-greifswald.de/bioinf/partitioned_odb11/ 
  * You can also prepare protein file of a close species, e.g. *Arabidopsis thaliana* and merge it with the OrthoDB file.

![Braker workflow][Braker_workflow]

[Braker_workflow]: ./Braker_workflow.PNG

*Braker workflow* from https://github.com/Gaius-Augustus/BRAKER 

## UTR annotation
You can use [GUSHR](https://github.com/Gaius-Augustus/GUSHR) which employs [GeMoMa](http://www.jstacs.de/index.php/GeMoMa)

## Functional annotation
[EggNog](https://github.com/eggnogdb/eggnog-mapper/wiki/) and [TRAPID](http://bioinformatics.psb.ugent.be/trapid_02/) can be used.





