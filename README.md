# VC Fund Success Predictor
Venture Fund Success Modeling With Deep Learning

---

## Overview
A venture capital firm, Alphabet Soup, recieves many funding applications from startups every day. This is an analyis using deep learning techniques, to create models which predict whether applicants will be successful if funded by Alphabet Soup.  

See full analysis details in the notebook [GC_venture_funding_with_deep_learning.ipynb](app/GC_venture_funding_with_deep_learning.ipynb)  


## DataSet
A single dataset of more than 34,000 organizations that have received funding from Alphabet Soup over the years:
- [applicants_data.csv](data/applicants_data.csv)
  - contains: `EIN,NAME,APPLICATION_TYPE,AFFILIATION,CLASSIFICATION,USE_CASE,ORGANIZATION,STATUS,INCOME_AMT,SPECIAL_CONSIDERATIONS,ASK_AMT,IS_SUCCESSFUL`  


## Assumptions & Analysis Process
1) `EIN` and `NAME` data is not essential and will be dropped
2) The first neural network model will use 2 hidden layers, with `relu` activation function
2) Technical deliverables:
    - prepare data (encode, scale, train/test sets) for use with neural network model
    - create compile and evaluate a binary classification model using a neural network
    - optimize the neural network model two more times looking for performance improvements


## Model Design And Optimizations

**Original Model - nn**  
The first model used 2 hidden layers, and used the mean of the number of inputs and number of outputs for the hidden node unit calculations. The hidden nodes used `relu` and the output node used `sigmoid`. The model was trained for 50 epochs and then evaluated on the test data set.

**Optimization Model - nn_A1**  
The first optimized model simply added a third hidden layer. As with the first, the hidden nodes each used the mean of the inputs and output count to determine the number of units per hidden layer, and each hidden layer used `relu` The output node used `sigmoid`. The model was trained for 50 epochs and then evaluated on the test data set.

**Optimization Model - nn_A2**  
The second optimized model tried a different approach, namely trying to reduce some noise from the feature set. The original feature set data was re-visited, and two feature columns, `STATUS` and `SPECIAL_CONSIDERATIONS`,looked to be entirely of the same values in each of their columns, and were therefore removed/dropped to simplify the features set somewhat. This reduced feature set was then encoded, scaled and split into train/test data, similar to the approach for the original data set. This reduced feature data was then used in the `nn_A2` model.  
The `nn_A2` model was created with two hidden nodes each the mean of the inputs and output count to determine the number of units per hidden layer, and each hidden layer used `relu`. The output node used `sigmoid`. This model was trained for 50 epochs on this reduced feature set, and then evaluated on the reduced test data set.  

## Summary Results

The comparison of each model's setup and results for loss and accuracy are captured in the table below. Neither of the optimization attempts dramatically improved the model. The `nn_A1` attempt had a nearly identical loss, and a barely higher accuracy. The `nn_A2` attempt seems to have made things worth, with both a higher loss and a lower accuracy.

| model | inputs | hidden | h1(units,act) | h2 | h3 | out(units,act) | Epoch | Loss | Acc |
| :--- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| nn | 116 | 2 | 58, relu | 29, relu | n/a | 1, sigmoid | `50` | `0.555` | `0.727` |
| nn_A1 | 116 | 3 | 58, relu | 29, relu | 15, relu | 1, sigmoid | `50` | `0.554` | `0.731` |
| nn_A2 | 113 | 2 | 57, relu | 29, relu | n/a | 1, sigmoid | `50` | `0.618` | `0.6858` |



Plots of the loss and accuracy for each model:   

![Elbow Comparisons](media/elbow_comparison.png)  


See full analysis details in the notebook [GC_venture_funding_with_deep_learning.ipynb](app/GC_venture_funding_with_deep_learning.ipynb) 

---

## Technologies

This challenge uses [python](https://www.python.org/) 3.7 and the following [built-in](https://docs.python.org/3/py-modindex.html) modules:
- [pathlib](https://docs.python.org/3/library/pathlib.html)

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