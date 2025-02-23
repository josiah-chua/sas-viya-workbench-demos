# Synthetic Data Privacy Risk (Singling Out Risk) Evaluation with Anonymeter

## Introduction to Synthetic Data

Synthetic data is artificially generated data that replicates the statistical properties of real-world datasets maintaining the utility of data for analysis and innovation.

### Why does synthetic data matter?
Synthetic data solves the challenge of sharing and analyzing sensitive data in a secure, privacy-preserving manner. By substituting real data with synthetic counterparts, organizations can:

* Enable innovation while adhering to stringent data protection regulations (e.g., GDPR, HIPAA).
* Reduce risks of data breaches and re-identification of individuals.
* Facilitate cross-organization collaborations and open-data initiatives.

## Privacy Risks in Synthetic Data
It is essential to evaluate and quantify these risks to ensure robust data protection. Three primary types of privacy risks are associated with synthetic data:

### **1. Singling Out**
The ability to isolate an individual record within the synthetic dataset corresponding to a real-world individual in the original dataset. 

*"There is only one person with attributes X, Y, and Z"*

### **2. Linkability**
There is a risk that an attacker can link records between the synthetic dataset and other datasets (e.g., external data sources) to re-identify individuals.

*"Records A and B belong to the same person"*

### **3. Inference**
Definition: The risk that sensitive attributes of an individual can be inferred from synthetic data.

*"A person with attributes X and Y also have Z" (inference)*

## Privacy Risks Evaluation
This workbench demo demonstrates how to utilize the open-source Python library [Anonymeter](https://github.com/statice/anonymeter) to evaluate the different possible privacy risks. It includes in-depth explanations of the different risks, how the library evaluates the risk, and how to interpret the results. 

**Currently the demo notebook is only for Singling Out Risk. The other two will be added in the future.**

## Data
We shall be using data from the Adult Census Bureau database, made available  [here](https://archive.ics.uci.edu/dataset/2/adult) and released under license [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). This data was extracted from the 1994 Census Bureau database by Ronny Kohavi and Barry Becker (Data Mining and Visualization, Silicon Graphics).

We use this data as a basis to generate synthetic data and then calculate Singling Out risk against the generated data.  The data selected is for purposes of showing an example of how to calculate risk metrics.  Feel free to replace the data source with other datasets and modify the notebook to run privacy risk metrics on the same.

The notebook contains steps to pull the data.

## Pre-requisites
An Active SAS Viya Workbench license and environment.

Python packages required:

pmlb - used for fetching datasets from the Penn Machine Learning Benchmark.
anonymeter  - Open Source package to evaluate privacy risks of synthetic datasets

Package versions can be found in the [requirements.txt](./config/requirements.txt) file.

Install packages using the following command line command:

```
pip install -r config/requirements.txt
```

## Parameters

### Synthetic Data

This notebook does not generate the synthetic data from the dataset mentioned. It can be generated, using other methods such as this [SDM Notebook](/government/census-synthetic-data-generation/python/GMM_Adult_Census_Income_Data_Workbench.ipynb), or other methods such as [procedures available in SAS Viya / Workbench](https://github.com/sassoftware/sas-studio-custom-steps/blob/main/SDG%20-%20Generate%20Synthetic%20Data%20through%20GANs/extras/SDG%20-%20Generate%20Synthetic%20Data%20through%20GANs.sas) or SAS Data Maker.

The notebook will contain comments on where to enter the file path to the synthetic data.

## Output
Various evaluation metrics and plots that illustrate privacy risk of the synthetic data set.

### References
*   ["A Unified Framework for Quantifying Privacy Risk in Synthetic Data", M. Giomi et al, PoPETS 2023](https://arxiv.org/abs/2211.10459).
*   [Anonymeter PyPi package](https://pypi.org/project/anonymeter/)
*   Adult Census Bureau database, available  [here](https://archive.ics.uci.edu/dataset/2/adult), Ronny Kohavi (Consultant/Stanford) and Barry Becker (Silicon Graphics)

## Contact
*   Josiah Chua (josiah.chua@sas.com)

## Change Log
*   Version 1.0.0 (16DEC2024)
    *   Initial release on GitHub
