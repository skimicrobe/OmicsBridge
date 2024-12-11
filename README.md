# OmicsBridge

OmicsBridge is a workflow designed to characterize multi-omics signatures within multi-level clusters derived from integrated multi-omics data. More broadly, these multi-level clusters address the question: "What are the microbiome, enzyme, and metabolic signatures within the clusters associated with a given phenotype?" Additionally, they help answer: "Which signatures contribute to the enriched pathways related to the phenotype?"
This workflow can be applied in any domain of microbiome 
This repository contains all the code and processed datsets necessary to reproduce the results
Contact the author at suyeonkim [at] unomaha.edu. This version has been tested for OSX. 

*Note: This work is currently the process of manuscript preparation.*

----------------------------------------------------------------------
## Features 
1. Feature selection is applied to the multi-omics dataset to extract relevant signatures.
   - Used Kruskal-Wallis test at two significant levels (p-values < 0.01 and 0.05) to identify significantly different features across groups(any phenotpye) for each omics data.
   - Applied to the significant features from the Kruskal-Wallis test to confirm pairwise differences through Pairwise Wilcoxon Tests.
  
2. Similarity network
   - Distance matrix was used to calculate dissimilarity network, then convert to similarity network.
   - This is required step for further clustering steps.
  
3. K-nearest neighbor (kNN)
   - Determine _'k'_ for kNN network to refine the essential relationships.

4. Ledien clustering
  
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
The example of datasets went throughd data pre-processing steps, including, sample filtering, normalization, etc.

Note: The required input datasets are paired microbiome-metabolome data.
```
unzip sampledata.zip 
```
**Three output folders will be created when you unzip it:**
 1. `./sampledata/cooccurNetwork/`
 2. `./sampledata/ko/`
 3. `./sampledata/rawdata/`


## Guides to R scripts 
```
Rscript step1_featureSelection.R
```
Input: ```Metagenome```

