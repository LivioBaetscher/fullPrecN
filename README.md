# fullPrecN
## README

fullPrecN is designed to find and process cystein-rich peptides from spider transcriptomes. A HMM search is performed twice, using hmmcompete. The HMM scores are used in the filtering process. All sequences, that are not removed during the filtering, are post-processed. The sequences are trimmed, sorted according to the toxin subfamily, redundant sequences are removed. Finally remaining sequences in the subgroups are aligned using mafft. The -r option allows to keep all redundant sequences for further analysis. The -o option allows redirecting the main output.

allMatModel.hmm and allSigModel.hmm are the library files containing HMMs built and trained for known spider neurotoxin families. If these models are retrained the number of found sequences might increase.

hmmcompete is a program used for the HMM search process.

All the models and hmmcompete need to be copied into the working directory (the same directory where fullPrecN is located).

### USAGE

For a correct evaluation, the transcriptome needs to be assembled and translated into amino acid sequences. The users must make sure that the transcriptome is in the FASTA file format.
The program is then started with the bash command:
```shell
./fullPrecN -i <path/of/transcriptomeFasta> --sig <path/of/singalHMM> --mat <path/of/matureHMM>
```
The files are stored in the new generated directory "Results". This directory can be changed using the "-o" option.
If the "-r" option is chosen, the redundant sequences are not automatically removed in the output.
With the option "-a" no alignment is preformed.

### PROGRAMS NEEDED

[Perl 5](https://www.perl.org/), [MAFFT version 7](https://mafft.cbrc.jp/alignment/software/) and [HMMER3](http://hmmer.org/)

### NOTICE

The files fullPrecN and allSigModel.hmm have been developed in Switzerland by Livio Bätscher. hmmcompete and allMatModel.hmm was developed by Dominique Koua also in Switzerland.
Therefore, the files are protected by the swiss Urheberrechtsgesetz (URG) and the Urheberrechtsverordnung (URV). It is allowed to copy and use the files but the users must cite the authors.
