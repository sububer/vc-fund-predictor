# VC Fund Predictor
Venture Fund Success Modeling With Deep Learning

---

## Overview
A venture capital firm, Alphabet Soup, recieves many funding applications from startups every day. This is an analyis using deep learning techniques, to create a model which predicts whether applicants will be successful if funded by Alphabet Soup.  

See full analysis details in the notebook [GC_venture_funding_with_deep_learning.ipynb](app/GC_venture_funding_with_deep_learning.ipynb)  


## DataSet
A single dataset of more than 34,000 organizations that have received funding from Alphabet Soup over the years:
- [applicants_data.csv](data/applicants_data.csv)
  - contains: `EIN,NAME,APPLICATION_TYPE,AFFILIATION,CLASSIFICATION,USE_CASE,ORGANIZATION,STATUS,INCOME_AMT,SPECIAL_CONSIDERATIONS,ASK_AMT,IS_SUCCESSFUL`  


## Assumptions & Analysis Process
1) `EIN` and `NAME` data is not essential and will be dropped
2) Technical deliverables:
    - prepare data for use with neural network model
    - create compile and evaluate a binary classification model using a neural network
    - optimize the neural network model at least two more times looking for performance improvements


## Summary

**Original Model**  


**Model A1**  


**Model A2**  


Plots of the loss and accuracy for each model:   

![Elbow Comparisons](media/elbow_comparison.png)  


See full analysis details in the notebook [GC_venture_funding_with_deep_learning.ipynb](app/GC_venture_funding_with_deep_learning.ipynb) 

---

## Technologies

This challenge uses [python](https://www.python.org/) 3.7 and the following [built-in](https://docs.python.org/3/py-modindex.html) modules:
- [os](https://docs.python.org/3/library/os.html#module-os)

Additionally, it requires:
- [matplotlib](https://matplotlib.org/)
- [pandas](https://pandas.pydata.org/)
- [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/)
- [scikit-learn](https://scikit-learn.org/stable/index.html)
- [tensorflow](https://www.tensorflow.org/)
- [keras](https://keras.io/)



See [installation](#installation) below for specifics.

---

## Installation

You will need Python 3.7, that supports for this application to run. An easy way to install python 3.7 is to download and install [Anaconda](https://www.anaconda.com/products/individual). After installing anaconda, open a terminal/command-prompt, and setup a python 3.7 environment, and then activate it like so:

```
# create an anaconda python 3.7 environment
# name can be any friendly name to refer to your environment, eg 'dev'
conda create --name dev python=3.7 anaconda

# activating the environment
conda activate dev

# use pip to install the above modules, eg:
pip install python-dotenv
...etc...
```


---

## Usage

The analysis is presented within a [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/) notebook. To launch JupyterLab, from the root of this repo dirctory:

```
# within repo root 
$ jupyter lab
```
You can now open the notebook [GC_venture_funding_with_deep_learning.ipynb](app/GC_venture_funding_with_deep_learning.ipynb)  

---

## Contributors

[David Lopez](https://github.com/sububer)

---

## License

MIT