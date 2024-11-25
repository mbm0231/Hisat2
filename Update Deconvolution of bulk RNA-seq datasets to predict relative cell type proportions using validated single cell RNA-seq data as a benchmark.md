# Update Deconvolution of bulk RNA-seq datasets to predict relative cell type proportions using validated single cell RNA-seq data as a benchmark.


```
#!/bin/bash
#SBATCH --time 1:00:00
#SBATCH --job-name=Hisat2
#SBATCH --nodes=1
#SBATCH --ntasks=1
#SBATCH --cpus-per-task=16
#SBATCH --partition=jumbo
#SBATCH --mem=512GB
#SBATCH --mail-type ALL
#SBATCH --mail-user mbmo231@uky.edu,farman@uky.edu
#SBATCH -A cea_farman_s24cs485g
#index prefix
indexname=$1
indexdir=/project/farman_s24cs485g/mbmo231/${indexname}_index
fasta=${indexname}'.fasta'
#Hisat2 image location
Hisat2image=/share/singularity/images/ccs/conda/amd-conda2-centos8.sinf
singularity run --app hisat2221 /share/singularity/images/ccs/conda/amd-conda2-centos8.sinf hisat2-build -l -p 16 $indexdir/$fasta $indexdir/$indexname

```
