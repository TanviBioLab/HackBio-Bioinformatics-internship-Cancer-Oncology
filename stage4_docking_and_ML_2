 <!--StartFragment-->

**Docking and Pipeline Implementation-2**

Authors (@slack): Tanvi Thakur (@Jerry), Samreen Raza (@samRaza)

**Phase 1**

**Introduction**

High-throughput screening is critical in cancer therapy discovery, particularly with the NCI-60 cell line. Machine learning efficiently helps predict missing IC50 values by linking genetic traits to drug responses, enabling personalized medicine while addressing cost and data gaps. Genomics of Drug Sensitivity in Cancer project data were filtered to include 608 cancer cell lines and 111 medications with SMILES. The study included 138 genetic and 689 chemical characteristics, using an 8-fold cross-validation approach with a feed-forward neural network to predict log IC50 and random forest regression to evaluate performance. ML models accurately predicted drug reactions with R² values of 0.72 in cross-validation and 0.64 in independent tests. These algorithms can estimate missing IC50 values, connecting patient genetic features to drug sensitivity and enabling personalized treatment.


### **Methodology**

1. **Dataset Preparation:** Selected SK-MEL-2 from the GDSC1 dataset ( 402 entries), added SMILES from PubChem/DrugBank and removed entries with missing SMILES.

2. **Data Upload:** Imported the dataset (drug names, cell line descriptions, IC50 values), into a Pandas DataFrame.

3. **Descriptor Generation:** RDKit generated molecular descriptors (MolWt, TPSA, NumHDonors, and NumHAcceptors) from SMILES.

4. **Normalization:** Applied StandardScaler to normalize descriptors, for improved model performance.

**Model Training**

1. **Model Setup:** The dataset was prepped with training, using LN\_IC50 as the target and identifying the best regression model.

2. **Hyperparameter Tuning:** The selected model was optimized using PyCaret's tune\_model() function to enhance R² and predictive accuracy.


### **Results**

|                              |                |                   |                                             |                                                            
| :--------------------------: | :------------: | :---------------: | :-----------------------------------------: |
|     **Evaluation Stages**    |    **Metric**  |     **Value**     |              **Notes**                      |
|  ### **Performance Metrics** |       MAE      |      2.0286       |      Best performance among models          |   
|                              |       MSE      |      6.7541       |
|                              |        R²      |      0.0372       |  Slight positive correlation with LN\_IC50  |
            |
|       **Other Models**       |      Dummy     |     Higher MAE    |             Poor performance                |                                                               
                               |     Regressor  |                   |                                             | 
|                              |   Decision Tree|     Negative R²   |                  Ineffective                | 
            |
|       **Model Tuning**       |Hyperparameters |   alpha\_1:0.001  |  Optimized using tune\_model() function     |  
|                              |                |    alpha\_2:0.2   |                                             |
|                              |                |   lambda\_1:0.2   |                                             |
|                              |                |   lambda\_2: 0.2  |                                             |
            |
|     **Cross-Validation**     |    MeanMAE     |      2.0262       |         Limited explanatory power           | 
|                              |    MeanMSE     |      6.7329       |                                             |
|                              |    MeanRMSE    |      2.5744       |                                             |
|                              |     MeanR²     |      0.0389       |                                             |
            |
| **Test Dataset Performance** |      MAE       |      2.2017       |          Low predictive accuracy            |     
|                              |     RMSE       |      2.7960       |                                             |
|                              |       R²       |      0.0213       |                                             |
            |
| **Full Dataset Predictions** |      MAE       |      2.1070       |        Limited ability to explain variance  |
|                              |      MSE       |      7.0766       |                                             |                  
|                              |     RMSE       |      2.6602       |                                             |
|                              |       R²       |      0.0593       |                                             |
            |
|       **Visualization**      |R²(Scatter Plot)|      0.2445       |    Weak correlation, need for improvement   |


### **Table 1:** Evaluation Metrics and Model Performance Summary

### **Comparison with the target paper**

Only SMILES-based molecular descriptors gave low R² values (0.0372 for training, 0.0213 for testing), indicating poor prediction accuracy. However, integrating both genomic and chemical features significantly improved results, with R² values of 0.72 in cross-validation and 0.64 in blind tests. This shows that combining genomic and chemical data enhances predictive performance for drug response. 

**Conclusion**

Despite being the best performer, the Bayesian Ridge model showed limited predictive accuracy for IC50 values, with weak correlation and low R². Further refinement and alternative approaches are needed to improve predictive performance.

**Phase 2**

**Introduction (Paper)**

Histone deacetylase 11 (HDAC11) is important in cancer because it regulates gene expression by removing acetyl groups from histones, which causes chromatin condensation and transcriptional suppression. Its overexpression inhibits tumor suppressor genes, allowing unregulated cell proliferation. Inhibiting HDAC11 can reactivate these pathways, inducing apoptosis and stopping proliferation, making it an attractive target for cancer treatment. 

The Schrödinger Suite 2019 optimized proteins and prepared ligands in their deprotonated forms. Docking compound 5a with Glide resulted in RMSD values of 2.018 Å for HDAC1, 0.763 Å for HDAC6, and 0.369 Å for HDAC8. FT895, a selective inhibitor, demonstrated bidentate chelation with HDAC11, resulting in significant activity (IC50 = 365 nM) and anti-neuroblastoma action (EC50 = 3.6 µM). 

**Methodology**

1. Download or generate 3D models of the 11 HDAC subtypes from the PDB.

2. Identify proven inhibitors for each HDAC subtype from the literature, then add 50 phytochemicals from the prior step for 61 inhibitors.

3. Import protein structures and ligand libraries into PyRx or AutoDock Vina.

4. Create grid boxes around active/binding sites and dock all 61 drugs in triplicate against each HDAC subtype.

5. Determine the mean and standard deviation of the docking scores over three replicates.

6. Collect docking tables and visuals to summarize binding affinities and interactions.

**Results**

\
\


|             |                                       |                            |                     |                     |
| :---------: | :-----------------------------------: | :------------------------: | :-----------------: | :-----------------: |
| **PROTEIN** |              **LIGAND**               | **HIGHEST BINDING ENERGY** | **RMSD/ub** **(Å)** | **RMSD/lb** **(Å)** |
|      1      |      HDAC1\_65064\_uff\_E=325.39      |            -7.9            |          0          |          0          |
|      2      |    6wbw\_A\_9865515\_uff\_E=371.00    |            -7.4            |          0          |          0          |
|      3      |        HDAC3\_135\_uff\_E=62.95       |            -5.4            |          0          |          0          |
|      4      | HDAC4\_model1\_9865515\_uff\_E=371.00 |            -8.8            |          0          |          0          |
|      5      |     HDAC5\_6918837\_uff\_E=454.67     |            -7.9            |          0          |          0          |
|      6      | HDAC6\_model1\_5352062\_uff\_E=553.03 |            -9.6            |          0          |          0          |
|      7      |  HDAC7\_model1\_65064\_uff\_E=325.39  |            -7.2            |          0          |          0          |
|      8      |     HDAC8\_12136798\_uff\_E=356.48    |            -9.8            |          0          |          0          |
|      9      |     HDAC9\_9865515\_uff\_E=371.00     |            -9.4            |          0          |          0          |
|      10     |    HDAC10\_12136798\_uff\_E=356.48    |            -7.3            |          0          |          0          |
|      11     |    HDAC11\_71520717\_uff\_E=156.23    |            -8.4            |          0          |          0          |

**Table 2:** Overview of Top Binding Affinities and Molecular Properties for Docked Compounds Across 11 HDAC Subtypes.

**Conclusion**

The analysis revealed varying binding affinities, with the highest values suggesting potential candidates for further investigation. These findings contribute to our understanding of inhibitor interactions with HDAC enzymes and provide a foundation for future drug development efforts.

**References**

1. H.M. Berman, J. Westbrook, Z. Feng, G. Gilliland, T.N. Bhat, H. Weissig, I.N. Shindyalov, P.E. Bourne, The Protein Data Bank (2000) _Nucleic Acids Research_ 28: 235-242 <https://doi.org/10.1093/nar/28.1.235>.

2. Kim, S., Chen, J., Cheng, T., Gindulyte, A., He, J., He, S., Li, Q., Shoemaker, B. A., Thiessen, P. A., Yu, B., Zaslavsky, L., Zhang, J., & Bolton, E. E. (2023). PubChem 2023 update. _Nucleic acids research_, _51_(D1), D1373–D1380.

<https://doi.org/10.1093/nar/gkac956>

3. Knox, C., Wilson, M., Klinger, C. M., Franklin, M., Oler, E., Wilson, A., ... & Wishart, D. S. (2024). DrugBank 6.0: the DrugBank knowledgebase for 2024. _Nucleic acids research_, _52_(D1), D1265-D1275.

4. [Small-Molecule Library Screening by Docking with PyRx.](http://www.ncbi.nlm.nih.gov/pubmed/25618350) Dallakyan S, Olson AJ. _Methods Mol Biol._ 2015;1263:243-50. The full text is available at <https://www.researchgate.net/publication/273954875_Small-Molecule_Library_Screening_by_Docking_with_PyRx>

5. Jendele L, Krivak R, Skoda P, Novotny M, Hoksza D. PrankWeb: a web server for ligand binding site prediction and visualization. Nucleic Acids Res. 2019 Jul 2;47(W1):  W345-W349. doi: 10.1093/nar/gkz424. PMID: 31114880; PMCID: PMC6602436.

6. Elisabeth Coudert, Sebastien Gehant, Edouard de Castro, Monica Pozzato, Delphine Baratin, Teresa Neto, Christian J A Sigrist, Nicole Redaschi, Alan Bridge, The UniProt Consortium , Annotation of biologically relevant ligands in UniProtKB using ChEBI, _Bioinformatics_, Volume 39, Issue 1, January 2023, btac793, <https://doi.org/10.1093/bioinformatics/btac793>

7. h[**ttps://doi.org/10.3390/ijms21228828**](https://doi.org/10.3390/ijms21228828)

8. <https://jhoonline.biomedcentral.com/articles/10.1186/s13045-024-01551-8>

**Supplementary Files**

https\://github.com/TanviBioLab/HackBio-Bioinformatics-internship-Cancer-Oncology/tree/main/supplementary\_files\_stage4

\


<!--EndFragment-->
