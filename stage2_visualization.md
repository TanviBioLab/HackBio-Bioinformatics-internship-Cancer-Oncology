<!--StartFragment-->

**Modeling and Visualization**

**Authors** (@slack): Tanvi Thakur (@Jerry), Samreen Raza (@samRaza)

**Github** https://github.com/TanviBioLab/HackBio-Bioinformatics-internship-Cancer-Oncology/blob/main/stage2_visualization.md

**Introduction** 

Cellular tumor antigen ****p53 is a transcription factor that responds to DNA damage by halting the cell cycle, allowing time for repair. If repair fails, p53 triggers apoptosis to prevent damaged DNA from being passed on, reducing cancer risk **\[1]**. The human p53 protein consists of 393 amino acids with key domains: transcription activation domains (TAD1: 1-40, TAD2: 41-60), proline-rich region (61-93), DNA-binding domain (102-293), tetramerization domain (323-353), and C-terminal domain (364-393) **\[2]**. Mutations, particularly in key amino acids like R175, R248, and R273 **\[3]-\[4]**, are found in about 50% of human cancers **\[5]-\[6]**. This makes p53 a major focus in cancer research for potential therapies **\[1]**. 

**Methods**

1. SWISS-MODEL simplifies the process with integrated databases and software, making model construction and validation easier **\[7]**. Template selection, essential for accuracy, was aided by hidden Markov models to identify structurally similar templates **\[8]**. After evaluation, the most suitable template was chosen as shown in the table below. 

|              |            |              |                  |           |           |
| ------------ | ---------- | :----------: | :--------------: | :-------: | :-------: |
| **Template** | **Method** | **Coverage** | **Seq Identity** | **QMEAN** | **GMQUE** |
| 7xzz.1.K     | EM, 4.07A  |     1.00     |        100       |    0.93   |    0.54   |

2. AlphaFold2 integrates deep learning into protein structures in three phases: creating MSAs, refining them using Evoformer, and identifying 3D atom positions **\[9,10]**. Our results provide a PAE plot, which indicates general reliability but increased errors in residues 100-200 and 250-350. These locations may require additional validation or signal flexibility. 

**Results**

- **Modeling:** Swiss-Model findings reveal high quality:98.47% of residues in the favored region, and the MolProbity score is 0.62. Meanwhile, AlphaFold2 has strong confidence in its main structure but less in residues, indicating flexibility.

- **Domain: S**WISS-MODEL predicts only the DNA-binding domain, while AlphaFold2 predicts all domains.

- **Visualization & Accuracy**: The table below provides a summary of structure alignment performed with PyMOL **\[11]**.

|                           |                              |                 |            |                        |
| :-----------------------: | :--------------------------: | :-------------: | :--------: | :--------------------: |
|       **Structure**       |        **Comparison**        |   **RMSD (Å)**  |  **Atoms** |       **Remarks**      |
|         Apo (2OCJ)        | Homology model vs AlphaFold2 |  0.271 vs 24.49 | 156 vs 220 |    Large difference    |
|    Agonist-bound (4AGQ)   | Homology model vs AlphaFold2 |  0.323 vs 0.340 | 165 vs 161 |      Very similar      |
|  Antagonist-bound (1YCR)  | Homology model vs AlphaFold2 | 6.223 vs 10.855 |     16     | Significant difference |
| Alignment & Visualization | Homology model vs AlphaFold2 |      0.390      |     172    |     High similarity    |


### **Conclusion**

Swiss-Model, which uses verified templates, is reliable for widely studied proteins, providing more accuracy. AlphaFold, on the other hand, employs deep learning and is effective when no templates are available but not as precise. In this study, Homology modeling is more effective for p53, resulting in reduced RMSD as well as greater structural similarity.

**Supplementary files**

<https://github.com/TanviBioLab/HackBio-Bioinformatics-internship-Cancer-Oncology/tree/main/supplementary_files_stage2> 

\


**References**

\[1] Y. Huang _et al._, “An overview of the functions of p53 and drugs acting either on wild- or mutant-type p53,” _European Journal of Medicinal Chemistry_, vol. 265, p. 116121, Feb. 2024, doi:[ 10.1016/j.ejmech.2024.116121](https://doi.org/10.1016/j.ejmech.2024.116121).

\[2] A. C. Joerger and A. R. Fersht, “Structural biology of the tumor suppressor p53,” _Annu Rev Biochem_, vol. 77, pp. 557–582, 2008, doi:[ 10.1146/annurev.biochem.77.060806.091238](https://doi.org/10.1146/annurev.biochem.77.060806.091238).

\[3] W. A. Freed-Pastor and C. Prives, “Mutant p53: one name, many proteins,” _Genes Dev_, vol. 26, no. 12, pp. 1268–1286, Jun. 2012, doi:[ 10.1101/gad.190678.112](https://doi.org/10.1101/gad.190678.112).

\[4] X. Yue, Y. Zhao, Y. Xu, M. Zheng, Z. Feng, and W. Hu, “Mutant p53 in Cancer: Accumulation, Gain-of-Function, and Therapy,” _J Mol Biol_, vol. 429, no. 11, pp. 1595–1606, Jun. 2017, doi:[ 10.1016/j.jmb.2017.03.030](https://doi.org/10.1016/j.jmb.2017.03.030).

\[5] N. Rivlin, R. Brosh, M. Oren, and V. Rotter, “Mutations in the p53 Tumor Suppressor Gene: Important Milestones at the Various Steps of Tumorigenesis,” _Genes Cancer_, vol. 2, no. 4, pp. 466–474, Apr. 2011, doi:[ 10.1177/1947601911408889](https://doi.org/10.1177/1947601911408889).

\[6] L. Bouaoun _et al._, “TP53 Variations in Human Cancers: New Lessons from the IARC TP53 Database and Genomics Data,” _Hum Mutat_, vol. 37, no. 9, pp. 865–876, Sep. 2016, doi:[ 10.1002/humu.23035](https://doi.org/10.1002/humu.23035).

\[7] L. Bordoli, F. Kiefer, K. Arnold, P. Benkert, J. Battey, and T. Schwede, “Protein structure homology modeling using SWISS-MODEL workspace,” _Nat Protoc_, vol. 4, no. 1, pp. 1–13, 2009, doi:[ 10.1038/nprot.2008.197](https://doi.org/10.1038/nprot.2008.197).

\[8] Dalton, J. A., & Jackson, R. M. (2007). An evaluation of automated homology modelling methods at low target–template sequence similarity. _Bioinformatics_, _23_(15), 1901-1908.

\[9] P. Cramer, “AlphaFold2 and the future of structural biology,” _Nat Struct Mol Biol_, vol. 28, no. 9, pp. 704–705, Sep. 2021, doi:[ 10.1038/s41594-021-00650-1](https://doi.org/10.1038/s41594-021-00650-1).

\[10] Z. Yang, X. Zeng, Y. Zhao, and R. Chen, “AlphaFold2 and its applications in the fields of biology and medicine,” _Sig Transduct Target Ther_, vol. 8, no. 1, pp. 1–14, Mar. 2023, doi:[ 10.1038/s41392-023-01381-z](https://doi.org/10.1038/s41392-023-01381-z).

\[11] The PyMOL Molecular Graphics System, "PyMOL," \[Online]. Available: <https://www.pymol.org/>. \[Accessed: Sep. 15, 2024].

\


<!--EndFragment-->
