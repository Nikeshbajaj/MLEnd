MLEnd Datasets - Documentation!
===================

Links::
  *  **[Homepage](https://MLEndDatasets.github.io)** 
  *  **[Documentation](https://mlend.readthedocs.io/)**
  *  **[Github](https://github.com/MLEndDatasets)**
  *  **[PyPi - project](https://pypi.org/project/mlend/)** 
  *  _ **Installation:** [pip install mlend](https://pypi.org/project/mlend/)

.. image:: https://MLEndDatasets.github.io/assets/imgs/mlend_logo.png
 :width: 400px

<br>

.. image:: https://readthedocs.org/projects/mlend/badge/?version=latest
  :target: https://mlend.readthedocs.io/en/latest/
  :alt: Documentation Status
.. image:: https://img.shields.io/pypi/v/mlend
   :alt: PyPI - Version
.. image:: https://static.pepy.tech/personalized-badge/mlend?period=total&units=international_system&left_color=black&right_color=blue&left_text=downloads
 :target: https://pepy.tech/project/mlend
.. image:: https://img.shields.io/pypi/dm/mlend
  :target: https://pypi.python.org/pypi/mlend
  :alt: PyPI - Downloads

.. important::
    Version: 1.0.0.2 | Released on 14 Nov 2023
    

:Authors:
    Nikesh Bajaj,
    Jesús Requena Carrión
:Home: https://MLEndDatasets.github.io





Installation
-----

**Requirement**:  numpy, matplotlib, scipy.stats, spkit

with pip
-----

  
::
  
  pip install mlend


Update with pip
-----
                        
::
  
  pip install mlend --upgrade


Spoken Numerals
=======


Download data
-----
                        
::
  
  import mlend
  from mlend import download_spoken_numerals, spoken_numerals_load
  
  subset = {'Numeral':[1,100],'Intonation':['neutral']}
  datadir = download_spoken_numerals(save_to = '../MLEnd', 
                                     subset = subset,verbose=1,overwrite=False)




Download full dataset
To download full dataset, use empty subset, as in following piece of code:

::
  
  import mlend
  from mlend import download_spoken_numerals, spoken_numerals_load
  
  subset = {}
  datadir = download_spoken_numerals(save_to = '../MLEnd', 
                                     subset = subset,verbose=1,overwrite=False)



Load the Data and benchmark sets
-----
                        
::
  
  import mlend
  from mlend import download_spoken_numerals, spoken_numerals_load
  
  subset = {'Numeral':[1,100],'Intonation':['neutral']}
  datadir = download_spoken_numerals(save_to = '../MLEnd', 
                                     subset = subset,verbose=1,overwrite=False)
  
  TrainSet, TestSet, MAPs = spoken_numerals_load(datadir_main = datadir, 
                               train_test_split = 'Benchmark_A',
                                verbose=1,encode_labels=True)





Contacts:
-----
                        
* **Jesús Requena Carrión**
* Queen Mary University of London

* **Nikesh Bajaj**
* Queen Mary University of London
* n.bajaj[AT]qmul.ac.uk, n.bajaj[AT]imperial[dot]ac[dot]uk

______________________________________
