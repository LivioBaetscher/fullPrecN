# fullPrecN
README

fullPrecN is a tool, which is searching for full precursor or fragments of spider neurotoxins in transcriptomic data.

allMatModel.hmm and allSigModel.hmm are the library files containing the per-built models. If these models are retrained the number of found sequences might increase.

hmmcompete is a program used for the HMM search process.

hmmsort is the main program that takes care of the selection, formating and output process.

USAGE

For an correct evaluation, the transcriptome needs to be annotated and translated into amino acid sequences. The users must make sure that the transcriptome is in the FASTA file format.
The program is then started with the bash command:

./fullPrecN <path/of/transcriptomeFasta>

All results will be stored in the directory where fullPrecN is located.

NOTICE

The files fullPrecN, hmmsort and allSigModel.hmm have been developed in Switzerland by Livio Bätscher. hmmsort and allMatModel.hmm was developed by Dominique Koua also in Switzerland.
Therefore, the files are protected by the swiss Urheberrechtsgesetz (URG) and the Urheberrechtsverordnung (URV). It is allowed to copy and use the files but the users must cite the authors.
