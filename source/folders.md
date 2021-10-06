# Folder structure

Your project should be organized the following way :

```
├── config
│   ├── config.yaml
│   └── samples.tsv
├── resources # Contains input files
│   ├── 1.1-fluo-ceq8000 # SHAPE data from ceq8015
│   ├── 1.2-fluo-ce # SHAPE data in a tsv format readable by QuShape
│   ├── sequence1.fa # Reference sequences of the studied RNA
│   ├── ... 
│   └── sequenceN.fa
├── results # Intermediary and analysed data
│   ├── 2-qushape
│   ├── 3.1-reactivity
│   ├── 3.2-normreact
│   ├── 4.1-aggreact
│   ├── 4.2-aggreact-ipanemap
│   ├── 5.1-ipanemap-config
│   ├── 5.2-ipanemap-out
│   ├── 5.3-structure
│   └── 5.4-varna 
└── workflow # Scripts used for data treatement
```

config
: This folder contains the two main configuration files:  `config.yaml` Which contains general configuration of the pipeline and `samples.tsv` Which contains informations about each sample

resources
: Folder containing input files. Those file can be imported from external folder
using `probe_file` and `control_file` fields in `samples.tsv` or you can
directly add file naming them using the schema in
`config.yaml->format->[control_]condition` sequences files can have abritrary
name, since they must be declared in `config.yaml` in the `sequences` section.

    1.1-fluo-ceq8000
    : Raw sequencing data in the original ceq8015 format

    1.2-fluo-ce
    : Sequencing data in a tsv format readable by QuShape

results
: Contains intermediary and final results from data treatement.

    2-qushape
    : Contains qushape projects. Those project can be generated automatically by the
    pipeline or imported using `qushape_file` field in `samples.tsv`.
    
    3-reactivity
    : Contains reactivity extracted automatically from qushape project, once the
    have been analysed
    
    3.2-normreact
    : Contains Normalized reactivity 
    
    4.1-aggreact
    : Contains aggregated reactivity : each replicate with the same conditions are
    aggregated together
    
    5.3-structure
    : Secondary structures generated by IPANEMAP in .dbn format
    
    
    5.4-varna
    : Secondary structures generated by IPANEMAP in .varna format