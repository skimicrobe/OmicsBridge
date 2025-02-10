# Introduction

OmicsBridge is a workflow designed to characterize multi-omics signatures within multi-level clusters derived from integrated multi-omics data. More broadly, these multi-level clusters address the question: "What are the microbiome, enzyme, and metabolic signatures within the clusters associated with a given phenotype?" Additionally, they help answer: "Which signatures contribute to the enriched pathways related to the phenotype?"
This workflow can be applied in any domain of microbiome study. 
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

### Getting Started:
![Overview](https://github.com/skimicrobe/OmicsBridge/blob/main/OverviewWorkflow.png)

We present a novel multi-level clustering approach to characeterize microbiome-based signatures using multi-omics data. 

##
#### Step 1. Feature Selection on omics data 
You need to determine the significant features for each input data (meta-omics data or processed omics data) using Kruskal Wallis test among independent groups. 
The significant features are determined using two levels of p-values (0.01 and 0.05). The following script is example script to conduct this step. 

```
Rscript step1_featureSelection.R
```
_Input_: raw meta-omics abundance profile \
_Output_: significant featured meta-omics abundance profile 

##
#### Step 2. Identification of multi-level clusters 
To identify the multi-level clusters, we have several steps to reach our goal. 
##### 2-1. Calculating distance between samples for each omics data and then constructing sample-to-sample similarity network 
First, the various distance metrics are used to calculate the distance between samples. Depending upon the data, the different metrics can be choosed. Here is the example of script for constructing similarity network.

```
Rscript step2_constructingNetwork.R
```
_Input_: significant featured meta-omics abundance profile \
_Output_: matrix for similarity network 

##
##### 2-2. Main integration analysis
The goal of this data integration analysis is to identify the multi-level clusters. 
The main strategy is first consturcting the weighted k-nearest neighbor (kNN) graph for the similarity matrix to retain the most relevant connections.
Successive rounds of Ledien clustering, prepare using similairty matrices derived from different data types, allow this approach to iteratively refine sample groupings. 
Note that this strategy is implemented with two strategies to explore the influence of data type order on the clustering outcomes. 
By incorporating all three omics layers, the final clusters are based on the collective results from each-omics data type and are less prone to the biases inherentin single-omics analyses. 

#### Step 3. Multi-omics signature analysis 



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
Input: ```Any pre-processed omics data```
