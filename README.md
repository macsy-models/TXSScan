# TXSScan: annotation of bacterial protein secretion systems

This set of MacSyFinder's models are dedicated to the genomic detection of bacterial secretion systems, and of evolutionarily related appendages. 
The systems that can be detected are the following: 

- Archaeal-T4P: the set of archeal type IV pili, comprising the archaeal flagellum (or archaeallum), the UV-induced pilus Ups, the bindosome Bas, etc... 
- ComM: the competence machinery found in monoderms, including the classical Bacillus machinery
- MSH: the mannose-sensitive hemagglutinin pilus
- T1SS: the type I secretion system 
- T2SS: the type II secretion system  
- T3SS: the type III secretion system  
- T4aP: the type IV pilus, sometimes also called the Type IVa pilus
- T4bP: the type IVb pilus, comprising the R64 thin pilus, toxin-coregulated pilus (TCP), bundle-forming pilus (Bfp), longus pilus, and Cof pilus
- pT4SSt, pT4SSi: two different types of type IV secretion systems involved in protein secretion (based on Mating Pair Formation type t and i respectively).
- T5aSS, T5bSS, T5cSS: three different types of type V secretion system, namely the autotransporter (T5aSS), the two-partner secretion system (T5bSS) and the trimeric secretion system (T5cSS). 
- T6SSi, T6SSii, T6SSiii: three variants of the type VI secretion system, namely the broadly distributed T6SSi, the one discovered in Francisella (T6SSii) and the one discovered in Bacteroidetes (T6SSiii).  
- Flagellum: the bacterial flagellum, related to the T3SS. Note: components detected with this model are sufficient to distinguish between the flagellum and the related T3SS, but do not fully annotate the flagellar components. 
- Tad: the Tad (thigh-adherence) pilus
- T9SS: the type IX secretion system


This set of models corresponds to those published in 2016 in Scientific Reports and in 2019 in Plos Biology (see below for full reference), updated to the format to enable systems search with **MacSyFinder version 2**. 


This new version : 

* is the combination of TXSScan and TFFscan
* it incorporate the new model for the TFF-SF from the TFFscan
* a subdivision of the models for archaea and bacteria and diderm and monoderm was implemented in the architecture (NB: some model in the diderm folder works also in monoderm, e.g. T4aP, Tad, some TXSS)

To summarize : 

|TXSScan  | | #HMM profiles | #Models |
| ------ | ---- | ------ | ------ |
|TXSScan v1.1.0 | latest | 341 | 26 |
|TXSScan v1.0.0 | [Sci Rep 2016](https://www.nature.com/articles/srep23080) | 205 | 22 |


## Installation and Usage with MacSyFinder

First, the `macsyfinder` program should be [installed](http://macsyfinder.readthedocs.io/en/latest/). This will also install the `macsydata` tool that enables to easily install this package of MacSyFinder models from this repository. 


The basic commands to run are then:

    macsydata install TXSScan


to install the TXSScan package. 

    macsyfinder --db-type ordered_replicon \
		--sequence-db myproteins.fasta \
		--models TXSScan system 		


to run the search on your favorite organism's genom, where `system` is one or multiple systems listed above, or `all` to search for all the above listed systems
(see [MacSyFinder's documentation](http://macsyfinder.readthedocs.io/en/latest/)). 


It has to be noted that to ensure the highest annotation specificity, it is recommended to search for **all** systems in the package at once. 


## References

- Abby Sophie S., Néron Bertrand, Ménager Hervé, Touchon Marie, Rocha Eduardo P. C.
  (2014).
  MacSyFinder: A Program to Mine Genomes for Molecular Systems with an Application to CRISPR-Cas Systems.
  PLoS ONE, 9 (10), pp. e110726.
  [doi:10.1371/journal.pone.0110726](http://dx.doi.org/10.1371/journal.pone.0110726)


- Denise Rémi, Abby Sophie S., Rocha Eduardo P. C. (2019). 
  Diversification of the type IV filament superfamily into machines for adhesion, protein secretion, DNA uptake, and motility.
  PLoS Biology 17(7): e3000390.
  [doi:10.1371/journal.pbio.3000390](https://doi.org/10.1371/journal.pbio.3000390)
  

- Abby Sophie S., Cury Jean, Guglielmini Julien, Néron Bertrand, Touchon Marie, Rocha Eduardo P. C.
  (2016).
  Identification of protein secretion systems in bacterial genomes.
  Scientific Reports, 6, pp. 23080.
  [doi:10.1038/srep23080](http://dx.doi.org/10.1038/srep23080)

For more details on this set of models, see this reference: [Abby et al. 2016](http://dx.doi.org/10.1038/srep23080), Identification of protein secretion systems in bacterial genomes, Scientific Reports and  [Denise et al. 2019](https://doi.org/10.1371/journal.pbio.3000390), Diversification of the type IV filament superfamily into machines for adhesion, protein secretion, DNA uptake, and motility, PLoS Biology. 

NB: The HMM protein profiles included were either built de novo, or obtained from the [TIGRFAM](http://tigrfams.jcvi.org/cgi-bin/index.cgi) or [PFAM](http://pfam.xfam.org/) databases. Check the metadata file or reference above for more details. 
