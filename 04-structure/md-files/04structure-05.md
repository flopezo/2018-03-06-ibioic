## 04-Protein structure visualization and analysis practical

### 04-05 But what if we have no structure, can 3D structure be predicted from sequence?
The sequence-structure gap is BIG ([77 million sequences](http://www.ebi.ac.uk/uniprot/TrEMBLstats) vs [123K structures](http://www.rcsb.org/pdb/), so its quite likley that a specific protein of interest has no experimentally solved 3D structure. For such proteins it may be possible to predict the secondary and tertiary structure from the amino acids sequence. There are many different programs designed for structure prediction. In the 2016 [CASPS 12](http://www.predictioncenter.org/casp12/index.cgi) (Critical assessement of protein structure prediction) competition (essentially a bake-off for fold prediction programs), more than 100 different programs were tested, all with varing degress of success.


In this practical we will make predictions for two small proteins which do not have a known (experimentally solved) 3D structure.

| Uniprot ID  | Protein Description | Organism
|:------------- |:--------------- |:--------
A6NFH5 | Fatty acid-binding protein| Human|
Q93VI0| DNA-binding protein S1FA3| Arabidopsis|


```
>sp|A6NFH5|Fatty acid-binding protein 12 OS=Homo sapiens
MIDQLQGTWKSISCENSEDYMKELGIGRASRKLGRLAKPTVTISTDGDVITIKTKSIFKN
NEISFKLGEEFEEITPGGHKTKSKVTLDKESLIQVQDWDGKETTITRKLVDGKMVVESTV
NSVICTRTYEKVSSNSVSNS

```

```
>sp|Q93VI0|DNA-binding protein S1FA3 OS=Arabidopsis thaliana 
MAAEFDGKIESKGLNPGLIVLLVIGGLLLTFLVGNFILYTYAQKNLPPRKKKPVSKKKMK
KEKMKQGVQVPGE
```


This [list] (http://bip.weizmann.ac.il/toolbox/structure/3d.htm) provides a good summary of the many tools available for structure prediction. For this practical we will use tools that are relatively quick to give results. These might not be the 'best' tools but they will give you a feel for how such tools work. 

In this practical we will 

1. predict the secondary structure of the proteins using [Jpred4](http://www.compbio.dundee.ac.uk/jpred4/index.html) and [NetSurfP](http://www.cbs.dtu.dk/services/NetSurfP-1.1/)
2. predict the 3D structure of the protein using [MODELLER](https://swissmodel.expasy.org/).

----
####03-05-01 Secondary structure prediction

* [Jpred4](http://www.compbio.dundee.ac.uk/jpred4) is a web-based protein secondary structure and solvent accessibility prediction server based on the JNet algorithm (that users a neural network) with a published three-state (helix,strand, coil) prediction accuracy of 82%  [Drozdetskiy et al., 2015](https://doi.org/10.1093/nar/gkv332) 

* [NetSurfP](http://www.cbs.dtu.dk/services/NetSurfP-1.1/) is a server that predicts the surface accessibility and secondary structure of an amino acid sequence using a neural network [Petersen et al., 2009](https://doi.org/10.1186/1472-6807-9-51)

#####Exercise 4: [10 mins] Secondary structure prediction.  
Submit each of the sequences A6NFH5 and Q93VI0 to the Jpred and NetSurfP servers and compare the results. 

####Questions: 

1. Did Jpred operate in the same way for both structures?
2. What secondary structure elements are predicted for A6NFH5?
3. Are the predictions from each server the same for A6NFH5?
4. What secondary structure elements are predicted for Q93VI0?
5. Are the predictions from each server the same for Q93VI0?

Making secondary structure predictions gives us some understanding of the how the proteins might operate in 3D space. But to get a greater understanding of how sequence features influence protein function we need to know how these secondary structure elements fold together in 3D.

----
#### 03-04-02: Tertiary structure prediction

We will use [SWISS-MODEL](https://swissmodel.expasy.org) which is a fully automated protein structure homology-modelling server to make predictions for our two proteins. 

#####Exercise 5: [15 mins] Tertiary structure prediction.  
Submit each of the above sequences Q93VI0 and A6NFH5 to [SWISS-MODEL](https://swissmodel.expasy.org). 

##### Questions

1. What template is used to model A6NFH5 and what is the sequence similarity (sequence identity)?
2. What template is used to model A6NFH5 and what is the sequence similarity (sequence identity)?
3. What 3D folds are predicted for each of the sequences?
3. How do you evaluate the accuracy of the models you have built?



If you have more time, explore the use of some of the other prediction servers e.g. 

* [PSIPRED](http://bioinf.cs.ucl.ac.uk/psipred/): which provides a protein sequence analysis workbench, including secondary structure predictions and fold recognition. 

* [Phyre2](http://www.sbg.bio.ic.ac.uk/phyre2/): a server for protein modelling and prediction.

