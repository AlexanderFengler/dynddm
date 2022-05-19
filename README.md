# dynddm
Code for project in which drift depends on dynamical systems.

### Installation (local)

To run the code in this repo locally, install the following python packages into your enviroment with `pip`.
Here some code to generate a conda enviroment and install the necessary packages.

```
conda create --name dynddm python=3.7
conda activate dynddm
conda install pip
conda install jupyter

pip install matplotlib
pip install git+https://github.com/AlexanderFengler/ssm_simulators
```

### Installation (colab)

You can run the jupyter notebooks in colab, just click on the links below: 

- [tests_simulators](https://colab.research.google.com/github/AlexanderFengler/dynddm/blob/main/tests_simulators.ipynb)
- [drift_investigations](https://colab.research.google.com/github/AlexanderFengler/dynddm/blob/main/drift_investigations.ipynb)


### What's here ?

#### `test_simulators.ipynb`

The `test_simulators.ipynb` notebook provides a starting point to play around with the `ds_conflict_drift` model. 
The model assume the following form for the drift:

```
v(t) = w_target(t) * target_coherence + w_distractor(t) * distractor_coherence
```

where (equivalently for `w_distrator`), 

```
w_target(t; initial_position, fixed_point, slope) = (initial_position - fixed_point) * exp(-(slope*t)) + fixed_point 
```

The rest of the model follows the skeleton of a standard drift diffusion model.

Also available is the `ds_conflict_angle` model. This includes a collapsing bound but is otherwise identical to the `ds_conflict_drift` model.
