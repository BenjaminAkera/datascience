Tests of Association
=====================

Pearson's Correlation
---------------------

.. note::
  
  * **X, Explantory**: Continuous
  * **Y, Response**: Continuous
  * **Type**: Non-Parametric

.. code:: python
  
  import pandas as pd
  import scipy.stats as ss
  import matplotlib.pyplot as plt
  import seaborn as sns
  %matplotlib inline
  
  
  print ss.pearsonr(df3['depth'],df3['diameter'])
  sns.regplot(x='depth',y='diameter',data=df3, fit_reg=True)


Spearman's Rank Correlation
---------------------------

.. note::
  
  * **X, Explantory**: Continuous
  * **Y, Response**: Continuous
  * **Type**: Parametric