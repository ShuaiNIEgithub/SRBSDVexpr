# SRBSDVexpr
SRBSDV RNA transcripts counting with RNAseq

# Install
cd ${yourpath}
git clone https://github.com/ShuaiNIEgithub/SRBSDVexpr.git
cd SRBSDVexpr
conda env create -f SRBSDVexpr.yaml
conda activate SRBSDVexpr

# Start

# We have already built the reference genome index filename prefix using hisat2-build and prepared the gene annotation in GTF format for SRBSDV.
# These files have been saved to the install path of SRBSDVexpr.
genomeindex=`realpath ${yourpath}/SRBSDVexpr/data/genome.fa`
gtf=`realpath ${yourpath}/SRBSDVexpr/data/all.gtf`

#Run
bash ${yourpath}/SRBSDVexpr/SRBSDVexpr.sh -r ${genomeindex} -g ${gtf} -c ${your_cleandatapath}  -s  ${your_sampleinfo} -t ${threads}

#Usage:
#-r: The real path for the reference genome index filename prefix with hisat2-build has been downloaded to the install path of SRBSDVexpr.
#-g: The real path for the gene annotation with gtf format has been downloaded to the install path of SRBSDVexpr.
#-c: Directory containing all of the clean sequencing data.
#-s: Sample info. about your sequencing data - 3 colums (sampleid ID.R1.fa.gz ID.R2.fa.gz) - no header.
#-t: Number of threads to use for multiprocessing.

