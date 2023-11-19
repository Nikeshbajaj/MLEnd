MLEnd Datasets - Documentation!
===================

Links: **[Homepage](https://MLEndDatasets.github.io)** | **[Documentation](https://mlend.readthedocs.io/)** | **[Github](https://github.com/MLEndDatasets)**  |  **[PyPi - project](https://pypi.org/project/mlend/)** |     _ **Installation:** [pip install mlend](https://pypi.org/project/mlend/)

-----

Installation
-----

**Requirement**:  numpy, matplotlib, scipy.stats, spkit

with pip
-----

```
pip install mlend
```

update with pip
-----
                        
```
pip install mlend --upgrade
```

Spoken Numerals
=======


Download data
-----
                        
```
import mlend
from mlend import download_spoken_numerals, spoken_numerals_load

subset = {'Numeral':[1,100],'Intonation':['neutral']}
datadir = download_spoken_numerals(save_to = '../MLEnd', 
                                   subset = subset,verbose=1,overwrite=False)

```


Download full dataset
To download full dataset, use empty subset, as in following piece of code:

```
import mlend
from mlend import download_spoken_numerals, spoken_numerals_load

subset = {}
datadir = download_spoken_numerals(save_to = '../MLEnd', 
                                   subset = subset,verbose=1,overwrite=False)
```



Load the Data and benchmark sets
-----
                        
```
import mlend
from mlend import download_spoken_numerals, spoken_numerals_load

subset = {'Numeral':[1,100],'Intonation':['neutral']}
datadir = download_spoken_numerals(save_to = '../MLEnd', 
                                   subset = subset,verbose=1,overwrite=False)

TrainSet, TestSet, MAPs = spoken_numerals_load(datadir_main = datadir, 
                             train_test_split = 'Benchmark_A',
                              verbose=1,encode_labels=True)

```




Contacts:
-----
                        
* **Jesús Requena Carrión**
* Queen Mary University of London

* **Nikesh Bajaj**
* Queen Mary University of London
* n.bajaj[AT]qmul.ac.uk, n.bajaj[AT]imperial[dot]ac[dot]uk

______________________________________
