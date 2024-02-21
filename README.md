# TXSScan: annotation of bacterial protein secretion systems

This set of MacSyFinder's models are dedicated to the genomic detection of bacterial secretion systems, and of evolutionarily related appendages. 
The systems that can be detected are the following: 


- **T1SS**: the type I secretion system 
- **T2SS**: the type II secretion system  
- **T3SS**: the type III secretion system  
- **Flagellum**: the bacterial flagellum, related to the T3SS. Note: components detected with this model are sufficient to distinguish between the flagellum and the related T3SS, but do not fully annotate the flagellar components. 
- **T4aP**: the type IV pilus, sometimes also called the Type IVa pilus
- **T4bP**: the type IVb pilus, comprising the R64 thin pilus, toxin-coregulated pilus (TCP), bundle-forming pilus (Bfp), longus pilus, and Cof pilus
- **pT4SSt, pT4SSi**: two different types of type IV secretion systems involved in protein secretion (based on Mating Pair Formation type t and i respectively).
- **T5aSS, T5bSS, T5cSS**: three different types of type V secretion system, namely the autotransporter (T5aSS), the two-partner secretion system (T5bSS) and the trimeric secretion system (T5cSS). 
- **T6SSi, T6SSii, T6SSiii**: three variants of the type VI secretion system, namely the broadly distributed T6SSi, the one discovered in Francisella (T6SSii) and the one discovered in Bacteroidetes (T6SSiii).  
- **Tad**: the Tad (tight-adherence) pilus
- **T9SS**: the type IX secretion system found in Bacteroidetes
- **ComM**: the competence machinery found in monoderms, including the classical *Bacillus* machinery
- **MSH**: the mannose-sensitive hemagglutinin pilus
- **Archaeal-T4P**: the set of archeal type IV pili that include the archaeal flagellum (or archaeallum), the UV-induced pilus Ups, the bindosome Bas, etc... 

This set of models corresponds to those published in 2016 in Scientific Reports, in 2019 in Plos Biology, in 2024 in Nature Communications (see below for details and full references). 
They are all in the format required for **MacSyFinder version 2** (Néron et al. 2023, Peer Community Journal). 

This new version of TXSScan: 

* is the combination of TXSScan and TFFscan, with updates of TXSScan models from TFFscan
* updates the T6SSiii model as described in Bongiovanni 2024
* now excludes the T4SS models (except for protein secreting T4SS), as the updated conjugation models are now available in the [CONJscan package](https://github.com/macsy-models/CONJScan)
* a subdivision of the models for archaea and bacteria and diderm and monoderm was implemented in the architecture (NB: some models in the diderm folder could also work on monoderms, e.g. T4aP, Tad, some TXSS)

To summarize : 

|TXSScan  | | #HMM profiles | #Models |
| ------ | ---- | ------ | ------ |
|TXSScan v1.1.2 | latest | 282 | 20 |
|TXSScan v1.1.1 | [Sci Rep 2016](https://www.nature.com/articles/srep23080) and [Plos Biol 2019](https://doi.org/10.1371/journal.pbio.3000390) | 341 | 26 |
|TXSScan v1.0.1 | [Sci Rep 2016](https://www.nature.com/articles/srep23080) | 205 | 22 |


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

If you use MacSyFinder and the macsy-models developped for TXSS detection, please cite the corresponding references:

### For MacSyFinder

- Néron Bertrand, Denise Rémi, Coluzzi Charles, Touchon Marie, Rocha Eduardo P. C., Abby Sophie S.
  (2014).
  MacSyFinder v2: Improved modelling and search engine to identify molecular systems in genomes.
  Peer Community Journal, 3: e28. 
  [doi:10.24072/pcjournal.250](https://doi.org/10.24072/pcjournal.250)

- Abby Sophie S., Néron Bertrand, Ménager Hervé, Touchon Marie, Rocha Eduardo P. C.
  (2014).
  MacSyFinder: A Program to Mine Genomes for Molecular Systems with an Application to CRISPR-Cas Systems.
  PLoS ONE, 9 (10), pp. e110726.
  [doi:10.1371/journal.pone.0110726](https://doi.org/10.1371/journal.pone.0110726)

### For the models

TFFscan:

- Denise Rémi, Abby Sophie S., Rocha Eduardo P. C. (2019). 
  Diversification of the type IV filament superfamily into machines for adhesion, protein secretion, DNA uptake, and motility.
  PLoS Biology 17(7): e3000390.
  [doi:10.1371/journal.pbio.3000390](https://doi.org/10.1371/journal.pbio.3000390)
  
TXSScan original publication:

- Abby Sophie S., Cury Jean, Guglielmini Julien, Néron Bertrand, Touchon Marie, Rocha Eduardo P. C.
  (2016).
  Identification of protein secretion systems in bacterial genomes.
  Scientific Reports, 6, pp. 23080.
  [doi:10.1038/srep23080](https://doi.org/10.1038/srep23080)

For the update of the T6SSiii:

- Thibault R. Bongiovanni, Casey J. Latario, Youn Le Cras, Evan Trus, Sophie Robitaille, Kerry Swartz, Danica Schmidtke, Maxence Vincent, Artemis Kosta, Jan Orth, Florian Stengel, Riccardo Pellarin, Eduardo P. C. Rocha, Benjamin D. Ross & Eric Durand
  (2024).
  Assembly of a unique membrane complex in type VI secretion systems of Bacteroidota.
  Nature Communications, 15: 429.
  [doi:10.1038/s41467-023-44426-1](https://doi.org/10.1038/s41467-023-44426-1)

For more details on this set of models, see these references: [Abby et al. 2016](https://doi.org/10.1038/srep23080) and [Denise et al. 2019](https://doi.org/10.1371/journal.pbio.3000390). 

### Note on the profiles

The HMM protein profiles included in the above models were either built de novo, or obtained from the [TIGRFAM](http://tigrfams.jcvi.org/cgi-bin/index.cgi) or [PFAM](http://pfam.xfam.org/) databases. Check the metadata file or references above for more details.
