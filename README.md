# OmicsBridge

We present a novel multi-level clustering approachto characeterize microbiome signatures using multi-omics data. Two clustering strategies are implemented to explore the influence of order of omics data in the integration process.
By incorporating all three omics layers, the final clusters are based on the collective results from each-omics data type and are less prone to the biases inherent in single-omics analyses. 

This repository contains all the code and processed datsets necessary to reproduce the results
Contact the author at suyeonkim [at] unomaha.edu. This version has been tested for OSX. 

Note: The manuscript is currently under-reviewed.

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
Our pipeline contains 4 major steps: (A) construct a species co-occurrence network from microbiome profile data; (B) Analyze the co-occurrence network at three granularity levels; (C) Perform pathway enrichment analysis; (D) Compare enriched pathways betweeen two IBD datasets in each sample from healthy/diseased status. An overview of the computational pipeline is shown in below. 

### Main workflow
![Overview](https://github.com/skimicrobe/OmicsBridge/blob/main/OverviewWorkflow.png)

## Input data  
We provide the datasets that used in our mansucript! Please download the folder 'sampledata.zip' in the location you would like to use. 
```
unzip sampledata.zip 
```
**Three output folders will be created when you unzip it:**
 1. `./sampledata/cooccurNetwork/`
 2. `./sampledata/ko/`
 3. `./sampledata/rawdata/`
