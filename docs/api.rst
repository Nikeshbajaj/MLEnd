API -  Documentation
====================

mlend.download_spoken_numerals
-------------------------


Help on function download_spoken_numerals in module mlend.downloader:

download_spoken_numerals(save_to='../MLEnd', subset={}, verbose=1, overwrite=False, pbar_style='colab')
    Download Spoken Numerals Dataset.
    
    # Arguments
        save_to: loacal path where you want to store the data
                  relative to `../MLEnd/spoken_numerals/`).
        subset: subset of data to download. {'attribute_name':list_of_values to select}
                 subset = {'Numeral':[1,2]}, will download audio files of numerals 1 and 2 only
                 subset = {'Numeral':[1,2], 'Intonation':['excited','question'], 'Speaker':[1,2,3,4,5,6]}
                 subset = {} will download entire dataset
    
    # Raises
        ValueError:
         - in case keys in subset are not in ['Numeral', 'Intonation', 'Speaker']
         - in case values of any keys are not valid
    
    # Returns
    
    path: path where data is saved


mlend.download_hums_whistles
-------------------------

Help on function download_hums_whistles in module mlend.downloader:

download_hums_whistles(save_to='../MLEnd', subset={}, verbose=1, overwrite=False, pbar_style='colab')
    Download Hums and Whistles Dataset.
    
    # Arguments
        save_to: loacal path where you want to store the data
                  relative to `../MLEnd/hums_whistles/`).
        subset: subset of data to download. {'attribute_name':list_of_values to select}
                 subset = {'Song':['Potter','Frozen']}, will download audio files of Potter and Fronzen only with both Hums and Whistles
                 subset = {'Song':['Potter','Frozen'], 'Interpretation':['Hum']} will download audio files of Potter and Fronzen with Huming only
                 subset = {'Interpretation':['Whistle']} will download all the audio files of Whistling
                 subset = {} will download entire dataset
    
    # Raises
        ValueError:
         - in case keys in subset are not in ['Song', 'Interpretation', 'Interpreter']
         - in case values of any keys are not valid
    
    # Returns
    
    path: path where data is saved


mlend.download_london_sounds
-------------------------

Help on function download_london_sounds in module mlend.downloader:

download_london_sounds(save_to='../MLEnd', subset={}, verbose=1, overwrite=False, pbar_style='colab')
    Download London Sounds Dataset.
    
    # Arguments
        save_to: loacal path where you want to store the data
                  relative to `../MLEnd/london_sounds/`).
        subset: subset of data to download. {'attribute_name':list_of_values to select}
                 subset = {'Area':['british_museum'], 'Spot':['forecourt','greatcourt']}, will download audio files of British museum for two spots only 'forecourt','greatcourt'
                 subset = {'Area':['british_museum']} will download all the spots of British Museum
                 subset = {'Area':['british_museum'],'In_Out':['indoor']} will download all the indoor spots of British Museum
                 subset = {} will download entire dataset
    
    # Raises
        ValueError:
         - in case keys in subset are not in ['Area', 'Spot', 'In_Out']
         - in case values of any keys are not valid
    
    # Returns
    
    path: path where data is saved


mlend.download_yummy_small
-------------------------

Help on function download_yummy_small in module mlend.downloader:

download_yummy_small(save_to='../MLEnd', verbose=1, overwrite=False, pbar_style='colab')
    Download Yummy Small Dataset.
    
    # Arguments
        save_to: loacal path where you want to store the data
                  relative to `../MLEnd/yummy/`).
    
    # Returns
    
    path: path where data is saved


mlend.download_yummy
-------------------------

Help on function download_yummy in module mlend.downloader:

download_yummy(save_to='../MLEnd', subset={}, verbose=1, overwrite=False, pbar_style='colab', debug_mode=False)
    Download Yummy Full Dataset.
    
    # Arguments
        save_to: loacal path where you want to store the data
                  relative to `../MLEnd/yummy/`).
        subset: subset of data to download. {'attribute_name':list_of_values to select}
            subset = {'Diet':['vegetarian']}, will download image files of vegetarian dishes only
            subset = {'Diet':['vegan'], 'Home_or_restaurant':['home']} will download image files of vegan dishes cooked at home
            subset = {} will download entire dataset
    
    # Raises
        ValueError:
         - in case keys in subset are not in the attribuate list ['Diet', 'Home_or_restaurant', 'Cuisine' ]
         - in case values of any keys are not valid
    
    # Returns
    
    path: path where data is saved


mlend.download_happiness
------------------------

Help on function download_happiness in module mlend.downloader:

download_happiness(save_to='../MLEnd', verbose=1, overwrite=False)
    Download Happiness Dataset.
    
    # Arguments
        save_to: loacal path where you want to store the data
                  relative to `../MLEnd/happiness/`).
    
    # Returns
    
    path: path where data is saved


mlend.download_load_happiness
------------------------

Help on function download_load_happiness in module mlend.downloader:

download_load_happiness()
    Download Happiness Dataset.
    
    # Arguments
        save_to: loacal path where you want to store the data
                  relative to `../MLEnd/spoken_numerals/`).
    
    # Returns
    
    pandas dataframe


mlend.spoken_numerals_load
------------------------

Help on function spoken_numerals_load in module mlend.processing:

spoken_numerals_load(datadir_main='../MLEnd/spoken_numerals', train_test_split='Benchmark_A', verbose=1, encode_labels=True)
    Read files of Spoken Numerals Dataset and create training and testing sets.
    
    
    # Arguments
        datadir_main (str): local path where 'MLEndSND_audiofiles' directory is stored
                  relative to `../MLEnd/spoken_numerals/`).
        train_test_split (str): split type for training and testing
          - 'Benchmark_A': Speaker Independent Benchmark
             Training (70%) and Testing (30%) do not have any common speaker
          - 'Benchmark_B': Speaker Dependent Benchmark
             Training (70%) and Testing (30%) both sets have same speakers
          - 'Random' or 'random': random split woth 70-30
          - float (e.g. 0.8) (>0 and <1)
            random split with given fraction for training set.
            if train_test_split = 0.8, Training set will be 80% and Testing 20%
    
        encode_labels: (bool), if to encode labels
    
    # Raises
        ValueError:
         - if train_test_split is not str ['Benchmark_A', 'Benchmark_B', 'random'] or float (<1 and >0)"
    
    # Returns
        TrainSet: A dictionary with keys {'X_paths', 'Y', 'Y_encoded'}
        TestSet:  A dictionary with keys {'X_paths', 'Y', 'Y_encoded'}
          - 'X_paths' is list of paths for audio files
          - 'Y' is Nx3 np.array, column 0 for Numerals, 1 for Intonation and 2 for Speaker
          - 'Y_encoded' is Nx3 np.array same as 'Y', column 0 for Numerals, 1 for Intonation and 2 for Speaker
                each column is encoded as 0, 1, 2 ..
    
        MAPs : A dictionary of maps, if encode_labels is true, else an empty dictionary


mlend.hums_whistles_load
------------------------


Help on function hums_whistles_load in module mlend.processing:

hums_whistles_load(datadir_main='../MLEnd/hums_whistles', train_test_split='Benchmark_A', verbose=1, encode_labels=True)
    Read files of Hums and Whistles Dataset and create training and testing sets.
    
    
    # Arguments
        datadir_main (str): local path where 'MLEndHWD_audiofiles' directory is stored
                  relative to `../MLEnd/hums_whistles/`).
        train_test_split (str): split type for training and testing
          - 'Benchmark_A': Speaker Independent Benchmark
             Training (70%) and Testing (30%) do not have any common speaker
          - 'Benchmark_B': Speaker Dependent Benchmark
             Training (70%) and Testing (30%) both sets have same speakers
          - 'Random' or 'random': random split woth 70-30
          - float (e.g. 0.8) (>0 and <1)
            random split with given fraction for training set.
            if train_test_split = 0.8, Training set will be 80% and Testing 20%
    
        encode_labels: (bool), if to encode labels
    
    # Raises
        ValueError:
         - if train_test_split is not str ['Benchmark_A', 'Benchmark_B', 'random'] or float (<1 and >0)"
    
    # Returns
        TrainSet: A dictionary with keys {'X_paths', 'Y', 'Y_encoded'}
        TestSet:  A dictionary with keys {'X_paths', 'Y', 'Y_encoded'}
          - 'X_paths' is list of paths for audio files
          - 'Y' is Nx3 np.array, column 0 for Song, 1 for Interpretation, and 2 for Interpreter
          - 'Y_encoded' is Nx3 np.array same as 'Y', column 0 for Song, 1 for Interpretation and 2 for Interpreter
                each column is encoded as 0, 1, 2 ..
    
        MAPs : A dictionary of maps, if encode_labels is true, else an empty dictionary

                                                                                             
mlend.london_sounds_load
------------------------

Help on function london_sounds_load in module mlend.processing:

london_sounds_load(datadir_main='../MLEnd/london_sounds', train_test_split='Benchmark_A', verbose=1, encode_labels=True)
    Read files of London Sounds Dataset and create training and testing sets.
    
    
    # Arguments
        datadir_main (str): local path where 'MLEndLSD_audiofiles' directory is stored
                  relative to `../MLEnd/london_sounds/`).
        train_test_split (str): split type for training and testing
          - 'Benchmark_A': Fixed Benchmark
             Training (70%) and Testing (30%)
          - 'Random' or 'random': random split woth 70-30
          - float (e.g. 0.8) (>0 and <1)
            random split with given fraction for training set.
            if train_test_split = 0.8, Training set will be 80% and Testing 20%
    
        encode_labels: (bool), if to encode labels
    
    # Raises
        ValueError:
         - if train_test_split is not str ['Benchmark_A', 'random'] or float (<1 and >0)"
    
    # Returns
        TrainSet: A dictionary with keys {'X_paths', 'Y', 'Y_encoded'}
        TestSet:  A dictionary with keys {'X_paths', 'Y', 'Y_encoded'}
          - 'X_paths' is list of paths for audio files
          - 'Y' is Nx3 np.array, column 0 for Area, 1 for Spot, and 2 for In_Out
          - 'Y_encoded' is Nx3 np.array same as 'Y', column 0 for Area, 1 for Spot and 2 for In_Out
                each column is encoded as 0, 1, 2 ..
    
        MAPs : A dictionary of maps, if encode_labels is true, else an empty dictionary

                                                                              
mlend.yummy_small_load
------------------------

Help on function yummy_small_load in module mlend.processing:

yummy_small_load(datadir_main='../MLEnd/yummy', train_test_split='Benchmark_A', verbose=1, encode_labels=True)
    Read files of Yummy Dataset and create training and testing sets.
    
    
    # Arguments
        datadir_main (str): local path where 'MLEndHWD_audiofiles' directory is stored
                  relative to `../MLEnd/hums_whistles/`).
        train_test_split (str): split type for training and testing
          - 'Benchmark_A': Speaker Independent Benchmark
             Training (70%) and Testing (30%) do not have any common speaker
          - 'Random' or 'random': random split woth 70-30
          - float (e.g. 0.8) (>0 and <1)
            random split with given fraction for training set.
            if train_test_split = 0.8, Training set will be 80% and Testing 20%
    
        encode_labels: (bool), if to encode labels
    
    # Raises
        ValueError:
         - if train_test_split is not str ['Benchmark_A', 'random'] or float (<1 and >0)"
    
    # Returns
        TrainSet: A dictionary with keys {'X_list', 'Y', 'Y_encoded'}
        TestSet:  A dictionary with keys {'X_list', 'Y', 'Y_encoded'}
          - 'X_paths' is list of paths for audio files
          - 'Y' is Nx1 np.array,
          - 'Y_encoded' is Nx1 np.array same as 'Y', 0=rice 1=chips
    
        MAPs : A dictionary of maps, if encode_labels is true, else an empty dictionary

                                                                              
mlend.yummy_load
------------------------
                                                                              
Help on function yummy_load in module mlend.processing:

yummy_load(datadir_main='../MLEnd/yummy/', train_test_split='Benchmark_A', verbose=1, attributes_as_labels='all', encode_labels=False)
    Read files of Yummy Dataset and create training and testing sets.
    
    
    # Arguments
        datadir_main (str): local path where 'MLEndYD_images' directory is stored
                  relative to `../MLEnd/yummy/`).
        train_test_split (str): split type for training and testing
          - 'Benchmark_A': A predifined fixed split
             Training (70%) and Testing (30%)
          - 'Random' or 'random': random split woth 70-30
          - float (e.g. 0.8) (>0 and <1)
            random split with given fraction for training set.
            if train_test_split = 0.8, Training set will be 80% and Testing 20%
    
        attributes_as_labels: list of attribuetes as labels
          - attributes_as_labels = 'all' will return all the attribuetes as label
          - attributes_as_labels = ['Diet','Healthiness_rating'] will return Y_train and Y_test as Nx2 columns diet and healthiness rating as labels
    
        encode_labels: (bool), if to encode labels
          - Only 'Diet', 'Home_restaurent', 'Healthiness_rating' and 'Likeness' will be encoded and return as numpy array
          - regardless of selection of attribuetes for labels
    
    # Raises
        ValueError:
         - if train_test_split is not str ['Benchmark_A', 'random'] or float (<1 and >0)"
    
    # Returns
        TrainSet: A dictionary with keys {'X_list', 'Y', 'Y_encoded'}
        TestSet:  A dictionary with keys {'X_list', 'Y', 'Y_encoded'}
          - 'X_paths' is list of paths for audio files
          - 'Y' is NxC Pandas DataFrame,
          - 'Y_encoded' is Nx4 np.array encoded labels for Diet, Home_or_restaurent, Healthiness and Likeness in that order.
    
        MAPs : A dictionary of maps, if encode_labels is true, else an empty dictionary

mlend.happiness_load
------------------------
                                                                              
Help on function happiness_load in module mlend.processing:

happiness_load(datadir_main='../MLEnd/happiness', verbose=1, overwrite=False)
    Read Happiness Dataset.
    
    # Arguments
        save_to: loacal path where you want to store the data
                  relative to `../MLEnd/happiness/`).
    
    # Returns
       Pandas Dataframe

                                                                                             

