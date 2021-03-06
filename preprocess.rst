Feature Preprocessing & Generation
===================================

Numeric
--------
Feature Proprocessing
************************

**Scaling**
^^^^^^^^^^^^

Many ML algorithms require normalization or scaling. See more in here_.

.. _here: http://python-data-science.readthedocs.io/en/latest/normalisation.html#

**Outliers**
^^^^^^^^^^^^

Especially sensitive in linear models. They can be (1) removed manually by
defining the lower and upper bound limit, or (2) grouping the features into ranks.

**Transformation**
^^^^^^^^^^^^^^^^^^^^^^^^

This helps in non-tree based and especially neural networks. 
Helps to drive big values close to features' average value.

Using Log Transform ``np.log(1+x)``. Or Raising to the power of one ``np.sqrt(x+2/3)``

Another important moment which holds true for all preprocessings is that sometimes, 
it is beneficial to train a model on concatenated data frames produced by different preprocessings, or to mix models training differently-preprocessed data. 
Again, linear models, KNN, and neural networks can benefit hugely from this. 


Feature Generation
************************
Sometimes, we can engineer these new features using *prior knowledge and logic*, 
or *using Exploratory Data Analysis*.

Examples include:
  * multiplication, divisions, addition, and feature interactions
  * feature extraction
  
.. figure:: images/preprocess1.png
    :width: 400px
    :align: center

    Coursera: How to Win a Data Science Competition


Categorical & Ordinal
-----------------------
Ordinal features are categorical but ranked in a meaningful way.

Tree-Based Models
******************

**Label Encoding**: or conversion of category into integers.
  * Alphabetical order ``sklearn.preprocessing.LabelEncoder``
  * Order of appearance ``pd.factorize``
**Frequency Encoding**: conversion of category into frequencies.
    
.. code:: python
  
  ### FREQUENCY ENCODING
  
  # size of each category
  encoding = titanic.groupby('Embarked').size()
  # get frequency of each category
  encoding = encoding/len(titanic)
  titanic['enc'] = titanic.Embarked.map(encoding)
  
  # if categories have same frequency it can be an issue
  # will need to change it to ranked frequency encoding
  from scipy.stats import rankdata

Non-Tree Based Models
**********************
**One-Hot Encoding**: each category is one field of 1 & 0. Not good if too many categories in a feature. Need to store in sparse matrix.
  * Dummies: ``pd.get_dummies``
  * sklearn: ``sklearn.preprocessing.OneHotEncoder``

**Feature Interactions**: interactions btw categorical features
  * Linear Models & KNN


.. figure:: images/preprocess2.png
    :width: 400px
    :align: center

    Coursera: How to Win a Data Science Competition
    
    
    
Datetime
---------


Coordinates
-------------