# OmicsBridge

OmicsBridge is a workflow for characterizing the multi-omics signatures in multi-level clusters from integrated multi-omics data. More generally, the multi-level clusters answers the question "What are the microbiome, enzyme, and metabolic signatures in the clusters that are associated with phenotype?" Furthermore, "which signatures are contributing to the enriched pathways in relation to phenotype?"


This repository contains all the code and processed datsets necessary to reproduce the results
Contact the author at suyeonkim [at] unomaha.edu. This version has been tested for OSX. 

*Note: The work is currently in manuscript preparation.*

----------------------------------------------------------------------
## Features 
1. Pathway-based profile based on species co-occurring community 
2. Finding a robust pathway which are enriched for captured co-occurring community 
3. Easy to implement
----------------------------------------------------------------------
## Requirements
Software R (Download from [here](https://www.r-project.org/) )

----------------------------------------------------------------------
## Workflows
Our workflow contains three major steps: 
Step 1. Feature Selection on omics data  
Step 2. Identification of multi-level clusters
Step 3. Multi-omics signatuer analysis

### Main workflow
![Overview](https://github.com/skimicrobe/OmicsBridge/blob/main/OverviewWorkflow.png)
We present a novel multi-level clustering approachto characeterize microbiome signatures using multi-omics data. Two clustering strategies are implemented to explore the influence of order of omics data in the integration process.
By incorporating all three omics layers, the final clusters are based on the collective results from each-omics data type and are less prone to the biases inherent in single-omics analyses. 

## Input data  
We provide the datasets that used in our mansucript! Please download the folder 'sampledata.zip' in the location you would like to use. 
```
unzip sampledata.zip 
```
**Three output folders will be created when you unzip it:**
 1. `./sampledata/cooccurNetwork/`
 2. `./sampledata/ko/`
 3. `./sampledata/rawdata/`
