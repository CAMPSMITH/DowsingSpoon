# DowsingSpoon

A neural net model that predicts the success likelyhood of prospective ventures.

---

## Overview of the Analysis

The objective of this activity was to develop a model that was effective at predicting the success likelyhood of prospective venture.  Historical data of prior funded entities, their stats and their success was provided.  This data consisted of categorical and numerical metrics.  

To prepare the data, non-meaningful columns, such a *Name* and *EIN* were dropped.  **OneHotEncoder** was used to encode categorical fields.  **StandardScaler** was used to scale the data.  The original dataset was split into training and testing datasets.  

After the data was prepared, using the tensorflow keras library, a deep neural network model with 2 hidden layers and an output layer (named **original**) was created and trained using the trainig dataset.

Several alternate models were also evaluated:
* **Alt 1** - this model increased the number of nodes in the hidden layers
* **Alt 2** - this model increased the number of additional layers
* **Alt 3** - this model increased training epoch and used alternate activation and loss functions

The effectiveness of the models were evaluated using the model's **evaluate()** method on the test data set.

The models were saved in **h5** format files.

## Results

| Model | Layers | Trainable Nodes | Loss | Accuracy |
|-------|--------|-----------------|---------|--------|
| original | 3 | 8,529 | 0.5553 | 0.7291 |
| alt 1 | 3 | 62,721 | 0.6797 | 0.7321 |
| alt 2 | 6 | 73,473 | 0.5703 | 0.7300 |
| alt 3 | 6 | 8,699 | 0.1868 | 0.7245 |

## Summary
The first alternative model attempted to improve model performance by increasing the number of nodes in the hidden layers.  Increasing the size of the hidden layers did not appreciably improve the performance of the model.

The second alternative model attempted to improve model performance by increasing the number of hidden layers.  Adding additional hidden layers also did not appreciably improve the performance of the model.

It was noticed that 50 epochs might not have been sufficient to allow the first two alternative models to converge.  In third alternative model, a higher number of epochs was used.  In addition, an alternative set of activation functions and loss functions were used.  Despite these changes, the performance of the third model was also not appreciably better than the original model.  In fact, the precision was slightly lower than the original model. 

---

## Technologies

* **Pandas**  - A python library with advanced financial analysis tools.
* **sklearn** - An open-source Python library offers algorithms and models for building machine models.
* **tensorflow** - A python library that offers frameworks for building deep neural network machine learning models.

---

## Quickstart

1. Navigate to **[Google Colab](https://colab.research.google.com)** - Google Colab is a hosted Jupyter Botebook IDE that offers good support for TensorFlow and other machine learning framework.
2. Upload notebook **GC_venture_funding_with_deep_learning.ipynb** to your Google Colab environment.
3. Run the notebook to review model performance statistics and assessment.

## Contributors

*  **Martin Smith** <span>&nbsp;&nbsp;</span> |
<span>&nbsp;&nbsp;</span> *email:* msmith92663@gmail.com <span>&nbsp;&nbsp;</span>|
<span>&nbsp;&nbsp;</span> [<img src="images/LI-In-Bug.png" alt="in" width="20"/>](https://www.linkedin.com/in/smithmartinp/)

---

## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)