# Assessment-of-GO-based-protein-interaction-affinities-in-the-3-large-scale-human-coronavirus-family

The work focuses on assessing the host-pathogen 21 protein interaction affinity of the coronavirus family, having 44 different variants. In light of these 22 considerations, a GO-semantic scoring function is provided based on Gene Ontology (GO) graphs 23 for determining the binding affinity of any two proteins at the organism level. Based on the avail- 24 ability of the GO annotation of the proteins, 11 viral variants, viz., SARS-CoV2, SARS, MERS, Bat 25 coronavirus HKU3, Bat coronavirus Rp3/2004, Bat coronavirus HKU5, Murine coronavirus, Bo- 26 vine coronavirus, Rat coronavirus, Bat coronavirus HKU4, Bat coronavirus 133/2005, are consid- 27 ered from 44 viral variants.

Usage 

1. ss_comp.py: This file compute the semantic score for any given pair of the target protein. Take input as a list of target protein pairs as a json file. 
—-------------------—-------------------—------------------- 
Usage : python SS_comp.py <org> 
<org> : Target_Virus_Code : example: SARS2,MERS.. . as you prefer the name 
—-------------------—-------------------—------------------- 
Please download the SS_Computation directory as it is, change the input file as required, and change the annotation file to the new set of proteins. A sample input format is given in the Annotations directory. The script is in ‘scriptSS’ directory. The output file will be generated in the directory SCORES. for example, ‘Human_CoV.csv’ Next, you can move the resultant file to the input directory for the next step.
  
2. Host-Pathogen_Score_Computation.py computes the normalized score for each protein-protein interaction (viz. Host-Host, Host-Pathogen, and Pathogen-Pathogen Interaction). It takes ‘Human_CoV.csv’ file as input which contains all six GO annotation values for each protein pair and gives output ‘MR_HsPth_Norm.csv’ which is a normalized score for each protein interaction pair.
  
3. Host_Pathogen_Network_Analysis.py analyzed the computed host-pathogen interaction network for Human-nCoV protein pair and analyzed the number of nodes and edges at different threshold values.
  
4. Gordon_High_Quality_Data_Analysis.py computes the normalized score for respective protein pairs and compare it with the proposed dataset. It takes ‘MR_GordonHQ_Score.csv’ as input and computes the normalized score for each interacting pair. The program takes ‘MR_HsPth_Norm.csv’ as input and computes the
graph for different threshold score. It further takes ‘Gordon_HighQuality.csv’ as input which is a high-quality Human-nCoV protein interaction dataset proposed by Gordon et.al. and analyzed the intersected nodes and intersected edges with respect to our dataset at different threshold values.
  
5. Gordon_Total_Data_Analysis.py takes ‘MR_HsPth_Norm.csv’ as input and computes the graph for different threshold score. It further takes ‘Gordon_Data_V2.csv’ as input which is a high-quality Human-nCoV protein interaction dataset proposed by Gordon et.al. and analyzed the intersected nodes and intersected edges with respect to our dataset at different threshold values.
  
6. PeerJ_Data.py takes ‘MR_HsPth_Norm.csv’ as input and loads the graph for different protein pairs. It then takes ‘PIPE.csv’ and ‘SPRINT.csv’ as input and compute the intersected nodes and edges with respect to our dataset.
  
7. Total_Covid_Interactome_Analysis.py takes ‘MR_HsPth_Norm.csv’ as input and loads the graph for different protein pairs. It then computes the graph for entire human-coronavirus interactome at different threshold values and calculates the vulnerable human proteins for the specified threshold. Vulnerable human proteins at 0.1 threshold is calculated as example.
  
8. DCS_Computation.py computes drug consensus score for different drug which have the target proteins computed from different threshold. It takes ‘all.csv’ as input which contains the list of all the drugs along with the ids and gives the output file ‘Drug_DCS_Score_0.1.csv’ which contains all the drug along with their DCS score at different threshold. One at 0.1 threshold is given as example. Protein-Gene mapping is curated from Uniprot by submitting the protein list at different threshold.
