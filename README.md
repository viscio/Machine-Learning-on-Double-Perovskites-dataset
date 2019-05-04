# Machine-Learning-on-Double-Perovskites-dataset
Couple of machine learning scripts to predict the stability of novel double perovskites, from a (small) dataset of calculated properties. 

In this folder, you can find different Jupyter notebook: 

1) RF_stability_test.ipynb
Prediction of stability of double perovskites, using a Random Forest Classifier

2) RF_stability_test_GridSearch.ipynb
Same as before, but with grid search in order to optimize hyperparameters

3) RF_dist_hull.ipynb
Random Forest Regressor to predict the distance from the convex hull (in eV) of various double perovskites. 

4) dist_hull_KRR.ipynb
Same prediciton as 3), but using a Kernel Ridge Regression method

5) form_en_KRR.ipynb
Prediction of formation energies of double perovskites (first step for calculating materials stability), using Kernel Ridge Regression
