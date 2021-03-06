
# MELD

This repository contains a python package that implements _MELD_, a
fast moment estimation method for generalized latent Dirichlet model.
For the details of the method and the model, please see
http://arxiv.org/abs/1603.05324.

# Introduction

MELD stands for *M*oment *E*stimation for generalized *L*atent
*D*irichlet models.


## The model

The generalized latent Dirichlet model in MELD assumes the *p*
dimensional observation **_y_**<sub>_i_</sub> is a mixture of *k*
latent components, with mixture weight denoted as a Dirichlet
distributed latent variable **_x_**<sub>_i_</sub>. This model is also
known as a *mixed membership model*. In contrast to previous mixed
membership models, the new model allows each coordinate of
**_y_**<sub>_i_</sub> to take different variable types, including
categorical, continuous and integer-valued variables.

## Parameter estimation

The parameter estimation method developed in MELD uses a moment method
known as generalized method of moments (GMM). This method is in
contrast to previous parameter estimation approaches such as MCMC or
EM algorithms that require instantiations of latent variables. The new
GMM approach does not require instantiations of latent variables. By
encoding each coordinate of **_y_**<sub>_i_</sub> by a dummy variable,
our new approach calculates the *cross* moment matrices or tensors
among variables, with latent variables effectively marginalized
out. Parameter estimation is conducted using a fast coordinate descent
algorithm.

# About the folders

- `MELD` contains the implementation of the package.

- `demo1.py` is a detailed demo script to show how to use MELD to
  analyze categorical observations. In this demo, we simulate 20
  categorical variables each of which takes four different categories.
  It corresponds to the categorical simulation study in the archive
  paper.
  
- `demo2.py` is a demo script to show the application of MELD to mixed
  data types. In this demo, we simulate a situation where DNA sequence
  variations influence a quantitative trait. The trait could take
  either continuous value or integer value. We use MELD to detect
  which nucleotide locations are associated with the quantitative
  trait. This demo corresponds to the mix data type simulation study
  in the archive paper.

- `data` contains the simulated data that are generated by the two
  demo scripts.





