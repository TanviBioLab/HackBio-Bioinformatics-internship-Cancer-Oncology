<!--StartFragment-->

**Virtual Screening (VS)**

Author (@slack): Tanvi Thakur (@Jerry)

Virtual screening is a computational biology technique identifying prospective leads from a vast library of small compounds by integrating docking, and pharmacophore models. As a result, a method is utilized to determine the possible interactions between chemical substances and proteins that alter their function. This can be a significant phase in the initial stages of drug research \[1]. This can be classified into two categories. 

1. **Structure-Based VS**

The screening involves the identification of potential ligand-binding sites on the target protein. Therefore the binding site can be the active site in a protein/enzyme. This is useful when we have information about the target protein structure. 

2. **Ligand Based VS**

Identify possible candidates for experimental testing by using structure-activity data from known potent substances \[2]. Methods include similarity and structural searches, QSAR, and pharmacophore and 3D shape matching \[3]. 

|                                                                                                                                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                         | SBVS                                              |                 LBVS                           |
|-----------------------------------------------------------------------------|------------------------------------------------|
| Obtain Protein Structure (Known structure)                                  | Data collection (active compounds)             |
| Compound library of small molecules                                         | Pharmacophore modeling (model development)     |
| Dock each molecule into the protein’s active site (via computational tools) | Similarity & substructure searching            |
| Scoring (binding affinity evaluation)                                       | QSAR analysis (build model to predict biological activity) |
| Post-processing (compounds ranking based on binding score)                  | 3D shape matching (identify compounds with spatial arrangement) |
| Candidate selection (top-ranked compounds)                                  | Scoring and Ranking (based on similarity to known ligands with pharmacophore model) |
|                                                                             | Selection of candidates (top-ranked compounds) |

Table 1. Flowchart of different types of virtual screening \[4]

**Advantages and Future Developments**

Virtual screening is an important component in modern drug discovery, because of ongoing advancements in computational tools that fast and effectively determine potential drug candidates. This approach involves assessing the drug-likeness of compounds by targeting important factors related to pharmacokinetics, pharmacodynamics, and toxic effects \[5]. Apart from the benefits, there is still a need for enhancements such as establishing better descriptors that capture 3D characteristics without relying on specific conformations, improving de nove design methods to consider compound synthesizability, refining scoring function for better binding affinities prediction, and comparing biologically equal but chemically diverse compounds \[6].  

**Conclusion**

The main objective of VS is to find possible bioactive substances using computational methods. It mainly relies on the target protein's structure which is time-saving and cost-efficient or the identified bioactive ligand. Though this field is developing, difficulties with frequent usage still exist. Ongoing advances in algorithms and techniques, however, should increase lead finding and clinical candidate quality \[7,8].

**References**

1. Lavecchia, A., & Di Giovanni, C. (2013). Virtual screening strategies in drug discovery: a critical review. _Current medicinal chemistry_, _20_(23), 2839-2860.

2. Jahn, A., Hinselmann, G., Fechner, N., & Zell, A. (2009). Optimal assignment methods for ligand-based virtual screening. _Journal of cheminformatics_, _1_, 1-23.

3. Villoutreix, B. O., Renault, N., Lagorce, D., Sperandio, O., Montes, M., & Miteva, M. A. (2007). Free resources to assist structure-based virtual ligand screening experiments. _Current Protein and Peptide Science_, _8_(4), 381-411.

4. Kar, S., & Roy, K. (2013). How far can virtual screening take us in drug discovery?. _Expert Opinion on Drug Discovery_, _8_(3), 245-261.

5. Reddy, A. S., Pati, S. P., Kumar, P. P., Pradeep, H. N., & Sastry, G. N. (2007). Virtual screening in drug discovery-a computational perspective. _Current Protein and Peptide Science_, _8_(4), 329-351.

6. Lengauer, T., Lemmen, C., Rarey, M., & Zimmermann, M. (2004). Novel technologies for virtual screening. _Drug discovery today_, _9_(1), 27-34.

7. Scior, T., Bender, A., Tresadern, G., Medina-Franco, J. L., Martínez-Mayorga, K., Langer, T., ... & Agrafiotis, D. K. (2012). Recognizing pitfalls in virtual screening: a critical review. _Journal of chemical information and modeling_, _52_(4), 867-881.

8. Vyas, V., Jain, A., Jain, A., & Gupta, A. (2008). Virtual screening: a fast tool for drug design. _Scientia Pharmaceutica_, _76_(3), 333-360.

<!--EndFragment-->
