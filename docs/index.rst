MLEnd Datasets - Documentation!
===================

Links::
  *  **[Homepage](https://MLEndDatasets.github.io)** 
  *  **[Documentation](https://mlend.readthedocs.io/)**
  *  **[Github](https://github.com/MLEndDatasets)**
  *  **[PyPi - project](https://pypi.org/project/mlend/)** 
  *  **Installation:** [pip install mlend](https://pypi.org/project/mlend/)

.. image:: https://MLEndDatasets.github.io/assets/imgs/mlend_logo.png
 :width: 400px
 :target: https://MLEndDatasets.github.io/

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


MLEnd Spoken Numerals
=====================


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




MLEnd Hums and Whistles
============================

Download subset of data
----------------------

To download subset of the data, song ‘Potter’ from first five interepreters, that includes humming and whisteling, use following piece of code:

::
  
  import mlend
  from mlend import download_hums_whistles, hums_whistles_load
  
  subset = {'Song':['Potter'],'Interpreter':list(range(5))}
  datadir = download_hums_whistles(save_to = '../MLEnd', subset = subset,verbose=1,
                                   overwrite=False,pbar_style='colab')

Download full dataset
----------------------

To download full dataset, use empty subset, as in following piece of code:

::
  
  import mlend
  from mlend import download_hums_whistles, hums_whistles_load
 
  subset = {}
  datadir = download_hums_whistles(save_to = '../MLEnd', subset = subset,verbose=1,
                                  overwrite=False,pbar_style='colab')



Load the Data and benchmark sets
-----------------------------

After downloading partial or full dataset, mlend allows you to load the dataset with specified method of training and testing split. Note, mlend doesn’t read and load the audio files in memory, instead it reads the path of files, for further reading and cleaning data as per requirement of the model. For more details, check help(hums_whistles_load).


::

  import mlend
  from mlend import download_hums_whistles, hums_whistles_load
  
  subset = {'Song':['Potter'],'Interpreter':list(range(5))}
  datadir = download_hums_whistles(save_to = '../MLEnd', subset = subset,verbose=1,
                                   overwrite=False,pbar_style='colab')
  
  TrainSet,TestSet, MAPs = hums_whistles_load(datadir_main = datadir,
                                              train_test_split = 'Benchmark_A',
                                              verbose=1,encode_labels=True)


MLEnd London Sounds
=====================

Download subset of data
------------------------


To download subset of the data, only one area ‘British Meusum’ with two spots namely; ‘forecourt’,’greatcourt’, use following piece of code:

::
  
  import mlend
  from mlend import download_london_sounds, london_sounds_load
  
  subset = {'Area':['british_museum'], 'Spot':['forecourt','greatcourt']}
  
  datadir = download_london_sounds(save_to = '../MLEnd', subset = subset,pbar_style='colab')


This code will download data in given path (‘../MLEnd’) and returns the path of data as datadir (='../MLEnd/london_sounds')

Download full dataset
------------------------

To download full dataset, use empty subset, as in following piece of code:

::

  import mlend
  from mlend import download_london_sounds, london_sounds_load
  
  subset = {}
  datadir = download_london_sounds(save_to = '../MLEnd', subset = subset,pbar_style='colab')


Load the Data and benchmark sets
------------------------

After downloading partial or full dataset, mlend allows you to load the dataset with specified method (‘Benchmark A’ or ‘random’) of training and testing split. Note, mlend doesn’t read and load the audio files in memory, instead it reads the path of files, for further reading and cleaning data as per requirement of the model. For more details, check help(london_sounds_load).

::
  
  import mlend
  from mlend import download_london_sounds, london_sounds_load
  
  subset = {'Area':['british_museum'], 'Spot':['forecourt','greatcourt']}
  
  datadir = download_london_sounds(save_to = '../MLEnd', subset = subset,pbar_style='colab'))
  
  TrainSet,TestSet, MAPs = mlend.london_sounds_load(datadir_main = datadir,
                                              train_test_split = 'Benchmark_A', 
                                              verbose=1,encode_labels=True)




MLEnd Happiness
=======

Download dataset
------------------------

To download happiness dataset make sure to updgrade mlend library to version>1.0.0.2

::
 
  pip install mlend --upgrade



To download dataset, use following piece of code

::
  
  import mlend
  from mlend import download_happiness, download_load_happiness, happiness_load
  
  datadir = download_happiness(save_to = '../MLEnd')


Load dataset
------------

After downloading, to load dataset use following piece of code

::
  
  import mlend
  from mlend import download_happiness, download_load_happiness, happiness_load
  
  datadir = download_happiness(save_to = '../MLEnd')
  
  D = happiness_load(datadir)

Download and read dataset
------------

Alternately, use following piece of code to download and load data with one line

::
  
  import mlend
  from mlend import download_load_happiness
  
  D = download_load_happiness()
  
  D.head()


MLEnd Yummy
=============


Download Data: Small set-  Starter-kit
------------

Small Yummy dataset: To get started
To download small subset of the data, that includes 99 images of Rice and Chips, use following piece of code:

::
  
  import mlend
  from mlend import download_yummy_small, yummy_small_load
  
  baseDir = download_yummy_small(save_to = '../MLEnd')


This code will download data in given path (‘../MLEnd’) and returns the path of data as datadir (='../MLEnd/yummy')

To read dataset with trainig and testing split using pre-defined ‘Bechmark’ use following code:

::
  
  TrainSet, TestSet, Map = yummy_small_load(datadir_main=baseDir,train_test_split='Benchmark_A')


Download Data: Full
------------

To download full yummy dataset make sure to updgrade mlend library to version>1.0.0.2

To download full dataset, use following piece of code

::
  
  import mlend
  from mlend import download_yummy, yummy_load
  
  subset = {}
  
  datadir = download_yummy(save_to = '../MLEnd', subset = subset,verbose=1,overwrite=False)


It will download all the images (3K+) in folder ../MLEnd/yummy/MLEndYD_images directory



Download partial data
------------

Alternately, to download subset of data use following piece of code

::
  
  import mlend
  from mlend import download_yummy, yummy_load
  
  subset = {'Diet':['vegan'], 'Home_or_restaurant':['home']}
  
  datadir = download_yummy(save_to = '../MLEnd', 
                                    subset = subset,verbose=1,overwrite=False)



Load the Data with benchmark sets
------------

After downloading partial or full dataset, mlend allows you to load the dataset with specified method of training and testing split. Note, mlend doesn’t load the image files in memory, instead it reads the path of files, for further reading and cleaning data as per requirement of the model. For more details, check help(yummy_load).


::
  
 import mlend
 from mlend import download_yummy, yummy_load
 
 subset = {'Diet':['vegan'], 'Home_or_restaurant':['home']}
 
 datadir = download_yummy(save_to = '../MLEnd', 
                                    subset = subset,verbose=1,overwrite=False)

 TrainSet, TestSet, MAPs = yummy_load(datadir_main = datadir,encode_labels=True,)



HTTPError
------------

Downloding might raise HTTPError, if any of the image file, part of subset selection is not found to download. All the files are still being uploaded on cloud. To avoid this error, use following code:

:: 
  
  datadir, FILE_ERROR = download_yummy(save_to = '../MLEnd', 
                                   subset = subset,verbose=1,overwrite=False,debug_mode=True)



API
----------

.. toctree::
   :maxdepth: 2
   
   api



Contacts:
-----
                        
* **Jesús Requena Carrión**
* Queen Mary University of London

* **Nikesh Bajaj**
* Queen Mary University of London
* n.bajaj[AT]qmul.ac.uk, n.bajaj[AT]imperial[dot]ac[dot]uk

______________________________________
