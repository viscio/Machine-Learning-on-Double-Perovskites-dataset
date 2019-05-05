# Machine-Learning-on-Double-Perovskites-dataset
Couple of machine learning scripts (in jupyter notebook format) to predict the stability of novel double perovskites, from a (small) dataset of DFT (Density Functional Theory)-calculated properties. Since the type of material (and hence the lattice type, the number of atom species and their arrangement in the lattice) is fixed, thie idea is to try to predict stability starting from atomic properties (like their group and period, their electronegativity, their ionization energy, etc.). 

![alt text](https://github.com/viscio/Machine-Learning-on-Double-Perovskites-dataset/blob/master/DP_structure_spacegroup_225.png)

In this folder, you can find different Jupyter notebook: 

1) RF_stability_test.ipynb: prediction of stability of double perovskites, using a Random Forest Classifier. No hyperparameter tuning performed, since this is a first-stage test to see if a bare Random Forest can reach satisfying precision and recall for our categories (stable/not stable). Random Forest have been chosen given its robustness, its performance on smaller datasets, and for its ability to look at the "feature importance". The results show that the most important features are the ones that can be inferred from "chemical intuition" regarding the systems object of the study: that means, the atomic properties related to the atoms B1 and B2

2) RF_stability_test_GridSearch.ipynb: same as before, but with grid search in order to optimize hyperparameters

3) RF_dist_hull.ipynb: Random Forest Regressor to predict the distance from the convex hull (in eV) of various double perovskites. 

4) dist_hull_KRR.ipynb: same prediciton as 3), but using a Kernel Ridge Regression method

5) form_en_KRR.ipynb: prediction of formation energies of double perovskites (first step for calculating materials stability), using Kernel Ridge Regression
