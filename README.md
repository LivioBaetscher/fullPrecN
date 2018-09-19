# fullPrecN
## README

fullPrecN is designed to find and process cystein-rich peptides from spider transcriptomes. A HMM search is performed twice, using hmmcompete. The HMM scores are used in the filtering process. All sequences which are not removed during the filtering are post-processed. The sequences are trimmed, sorted according to the toxin subfamily. Redundant sequences are removed. Remaining sequences in the subgroups are aligned using mafft. The -r option allows to keep all redundant sequences for further analysis. The -o option allows redirecting the main output.

allMatModel.hmm and allSigModel.hmm are the library files containing HMMs which are built and trained for known spider neurotoxin families. If these models are retrained, the number of found sequences might increase.

hmmcompete is a program used for the HMM search process.

INSTALATION is a short explanation hoe to install the third party software and run a simple test.

ZhangJ.fasta is a fasta file from a study of Zhang et al. it contains spider neurotoxins and is needed to run a test.

All the models and hmmcompete need to be copied into the working directory (the same directory where fullPrecN is located).

### USAGE

For a correct evaluation, the transcriptome needs to be assembled and translated into amino acid sequences. The users must make sure that the transcriptome is in the FASTA file format.
The program is then started with the bash command:
```shell
./fullPrecN -i <path/of/transcriptomeFasta> --sig <path/of/singalHMM> --mat <path/of/matureHMM>
```
The files are stored in the newly generated directory "Results". This directory can be changed using the "-o" option.
If the "-r" option is chosen, the redundant sequences are not automatically removed in the output.
With the option "-a" no alignment is preformed.

The files “allMatModel.hmm” and “allSignalModel.hmm” contain the signal and mature peptide models which were generated with HMMER 3.0. The ending “.hmm” indicates, that the file contains profile HMM and has the same ending as in the HMMER manual. The model files can also be trained. Therefore, the user can build models with the hmmbuilt function and replace or add subfamilies or families. The only restriction for the training process is the fact, that the model name must be chosen like this: SN_XX_XX (X must be a number from zero to nine).

### PROGRAMS NEEDED

[Perl 5](https://www.perl.org/), [MAFFT version 7](https://mafft.cbrc.jp/alignment/software/) and [HMMER3](http://hmmer.org/)

### NOTICE

The files fullPrecN and allSigModel.hmm have been developed by Livio Bätscher. hmmcompete and allMatModel.hmm were developed by Dominique Koua, both in Switzerland.
Therefore, the files are protected by the swiss Urheberrechtsgesetz (URG) and the Urheberrechtsverordnung (URV). It is allowed to copy and use the files but the users must cite the authors.

### CYTE

For fullPrecN: Bätscher L, Kua D, Langenegger N, Nentwig W, Kuhn-Nentwig L. fullPrecN: Fully Automatized Neurotoxin Precursor Detection in Spider Transcriptomes, Based on HMM. Unpublished.
For hmmbuilt: Koua D, Kuhn-Nentwig L. Spider Neurotoxins, Short Linear Cationic Peptides and Venom Protein Classification Improved by an Automated Competition between Exhaustive Profile HMM Classifiers. Toxins. 2017;9:245.
For the fasta file with neurotoxin sequences: Zhang Y, Huang Y, He Q, Liu J, Luo J, Zhu L, Shanshan L, et al. Toxin diversity revealed by a transcriptomic study of Ornithoctonus huwena. PLoS One. 2014;9:e100682.
