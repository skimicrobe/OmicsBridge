# OmicsBridge

OmicsBridge is a workflow designed to characterize multi-omics signatures within multi-level clusters derived from integrated multi-omics data. More broadly, these multi-level clusters address the question: "What are the microbiome, enzyme, and metabolic signatures within the clusters associated with a given phenotype?" Additionally, they help answer: "Which signatures contribute to the enriched pathways related to the phenotype?"

This repository contains all the code and processed datsets necessary to reproduce the results
Contact the author at suyeonkim [at] unomaha.edu. This version has been tested for OSX. 

*Note: This work is currently the process of manuscript preparation.*

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

1. Feature Selection on omics data
2. Identification of multi-level clusters
3. Multi-omics signature analysis

### Main workflow
![Overview](https://github.com/skimicrobe/OmicsBridge/blob/main/OverviewWorkflow.png)

We present a novel multi-level clustering approachto characeterize microbiome signatures using multi-omics data. First, significant features are Two clustering strategies are implemented to explore the influence of order of omics data in the integration process.
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
