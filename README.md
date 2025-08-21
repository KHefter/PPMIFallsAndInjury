# Fall Frequency, Risk Factors, and Outcomes in Parkinson's Disease: A Cross-Sectional Analysis
R code used to analyze the relationship between fall frequency, fall outcomes (including injury and hospitalization), and a wide range of clinical variables in members of the PPMI cohort.

## Requirements and Dependencies 
No versions have been tested other than those listed below. 
- R, https://www.r-project.org/, version 4.5.0 
- dplyr, version 1.1.4
- tidyr, version 1.3.1
- ggplot2, version 3.5.2
- readxl, version 1.4.5
- knitr, version 1.50
- flextable, version 0.9.8
- magrittr, version 2.0.3
- patchwork, version 1.3.0
- ggridges, version 0.5.6
- stringr, version 1.5.1
- ggpubr, version 0.6.0
- aod, version 1.3.3
- gridExtra, version 2.3

All libraries are loaded within the code.

## Usage:
Code may be run all at once to create an html file, or cell by cell.

Data sources are listed in the header. 

The second r cell, 'LoadData' should be amended to match the user's repository location. The rest of the code may be run as written. Some variables may be unused. The final cell, 'customPlots' may be edited to show analyses of interest to the user. 

### Breakdown of code sections
Additional documentation is provided within the body of the code itself. 

The first four steps are for preprocessing, and should be run for every analysis. 

- **Step 1** of the code loads the data and performs preprocessing. This includes merging data from several different PPMI sources ('LoadData'). 
- **Step 2** includes deriving variables ('CombineSAAData', 'MapYears', 'getDemographicCategoricals', 'getFallFreqs', 'getFallOccurrence', and 'getInjuryVars'), and creating a list of variables to be used in the analysis ('labelVariables').
- **Step 3** preprocesses the dataframe more by removing white space and standardizing the formatting across columns.
- **Step 4** of the code subselects the cohort data.

The remaining steps are the bulk of the analysis, and may be run separately if desired. 

- **Step 5** performs the first two analyses described in the paper, studying the relationship between rates of falling, injury, and hospitalization between a healthy cohort, a cohort with prodromal PD cohort, and a cohort with sporadic PD. The first cell in this section, **BH**, provides the function used for Benjamini-Hochberg corrections and should be run every time. The other cells perform the statistical analyses then run the BH corrections. 
- **Step 6** of the code details the code used to study fall, injury, and hospitalization _within_ the cohort with sporadic PD as a function of years since diagnosis and as a function of NSD stage. Running the code should replicate figures shown in the paper. 
- **Step 7** creates the cross-sectional cohort and analyzes the relationships between never, rare, and frequent fallers and several clinical variables of interest. Details of cross-sectional cohort creation are listed in the documentation. Running this portion of the code should recreate graphs shown in the paper.

- The final cell, 'customPlots' may be tailored to study any variable of interest. The variable 'namelist' should be edited to include all variables of interest. Once run, the code will provide a series of graphs showing the relationship between the variables listed and the cross-sectional faller groups.

### Link to Relevant Paper
Code in this repository was used for the paper, https://www.medrxiv.org/content/10.1101/2025.08.05.25332959v1.full-text. 
### Acknowledgements
Code was written by Kat Hefter, with assistance from Joaquin Vizcarra.

This work was supported by the National Institute of Health (1T32NS091006-10 and 5T32NS091006-10), the Institute for Translational Medicine and Therapeutics of the Perelman School of Medicine at the University of Pennsylvania, and the Michael J. Fox Foundation (Write Now! Award). Study sponsors had no role in the data for the present study.

Protocol information for The Parkinson’s Progression Markers Initiative (PPMI) Clinical - Establishing a Deeply Phenotyped PD Cohort AM 3.2. can be found on protocols.io or by following this link: ttps://dx.doi.org/10.17504/protocols.io.n92ldmw6ol5b/v2. PPMI – a public-private partnership – is funded by the Michael J. Fox Foundation for Parkinson’s Research and funding partners, including 4D Pharma, Abbvie, AcureX, Allergan, Amathus Therapeutics, Aligning Science Across Parkinson’s, AskBio, Avid Radiopharmaceuticals, BIAL, BioArctic, Biogen, Biohaven, BioLegend, BlueRock Therapeutics, Bristol-Myers Squibb, Calico Labs, Capsida Biotherapeutics, Celgene, Cerevel Therapeutics, Coave Therapeutics, DaCapo Brainscience, Denali, Edmond J. Safra Foundation, Eli Lilly, Gain Therapeutics, GE HealthCare, Genentech, GSK, Golub Capital, Handl Therapeutics, Insitro, Jazz Pharmaceuticals, Johnson & Johnson Innovative Medicine, Lundbeck, Merck, Meso Scale Discovery, Mission Therapeutics, Neurocrine Biosciences, Neuron23, Neuropore, Pfizer, Piramal, Prevail Therapeutics, Roche, Sanofi, Servier, Sun Pharma Advanced Research Company, Takeda, Teva, UCB, Vanqua Bio, Verily, Voyager Therapeutics, the Weston Family Foundation and Yumanity Therapeutics.
