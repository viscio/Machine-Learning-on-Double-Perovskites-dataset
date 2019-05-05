# Machine-Learning-on-Double-Perovskites-dataset
Couple of machine learning scripts (in jupyter notebook format) to predict the stability of novel double perovskites, from a (small) dataset of DFT (Density Functional Theory)-calculated properties. Since the type of material (and hence the lattice type, the number of atom species and their arrangement in the lattice) is fixed, thie idea is to try to predict stability starting from atomic properties (like their group and period, their electronegativity, their ionization energy, etc.). 

![alt text](https://github.com/viscio/Machine-Learning-on-Double-Perovskites-dataset/blob/master/DP_structure_spacegroup_225.png)

Double perovskites have atoms arranged in a lattice as shown in the figure, with formula *A<sub>2</sub>B'B''C<sub>6</sub>*. A-atom are the green ones, C atoms are the red ones (the vertices of the octahedra that are drawn in the figure), and B'/B'' are atoms at the center of octahedras, arranged in an alternate fashion. 

**In this folder, you can find different Jupyter notebook:** 

1) **RF_stability_test.ipynb**: prediction of stability of double perovskites, using a *Random Forest Classifier*. No hyperparameter tuning performed, since this is a first-stage test to see if a bare Random Forest can reach satisfying precision and recall for our categories (stable/not stable). Random Forest have been chosen given its robustness, its performance on smaller datasets, and for its ability to look at the "feature importance". The results show that the most important features are the ones that can be inferred from "chemical intuition" regarding the systems object of the study: that means, the atomic properties related to the atoms B1 and B2. 

2) **RF_stability_test_GridSearch.ipynb**: same as before, but with *grid search* in order to optimize hyperparameters and get better predictions. 

3) **RF_dist_hull.ipynb**: instead of predicting two classes stable/not stable, here the machine tries to predict the physical quantity associated with stability, which is called "distance from hull". It's defined as an energy(in eV usually) per atom. Since it's a continuous quantity, the model here is a *Random Forest Regressor*. Random Forest have been chosen following the same criteria as in 1), with hyperparameter tuning for maximum efficiency. Here, the scoring method is Mean Absolute Error. 

4) **dist_hull_KRR.ipynb**: same value prediciton as 3), but using a *Kernel Ridge Regression* method. 

5) **form_en_KRR.ipynb**: even before stability, it's possible to define a "precursor" property, which is called formation energy. It's defined as the total energy difference between the compound and the sum of the total energies of the single elements taken alone. It's basically the energy that we "earn" forming the compound instead of keeping the elements separated. Again, a Kernel Ridge Regression method has been implemented for the predictions. 
