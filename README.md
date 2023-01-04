# Automated bioacoustic monitoring tool for gopher frogs (Lithobates capito)

## Summary

This project uses the [repeat interval-based bioacoustic identification tool (RIBBIT)](https://conbio.onlinelibrary.wiley.com/doi/epdf/10.1111/cobi.13718) from [OpenSoundscape](http://opensoundscape.org/en/latest/) to identify gopher frog calls in audio recording. The goal is to create a tool that can be used by conservationists to monitor endangered gopher frog populations and devise management plans. The RIBBIT algorithm will produce numeric scores on short clips of audio. The highest scoring clips can then be manually reviewed to confirm the presence of gopher frogs.

## Instalation and setup 

1. If you have not already, install [Python](https://www.python.org/downloads/) and [Jupyter](https://jupyter.org/install). 
1. Install [OpenSoundscape](http://opensoundscape.org/en/latest/). 
1. Setup a Python environment for the model in Terminal/Commandline: 

```
# Create a Python environment for opensoundscape: 
conda create --name env_name pip python=3.7 # (or another version number)

# Activate the environment: 
conda activate opensoundscape

# Install my_package using pip: 
pip install opensoundscape

# Get environment to show in jupyter 
python -m ipykernel install --user --name=env_name --display-name=env_name


# Deactivate the environment when you’re done using it: 
conda deactivate

```

If you later want to delete the environment: 

```
# delete environment
conda env remove --name myenv

# remove kernel for jupyter
# (while in base envr)
python -m jupyter kernelspec list # list environment kernels 
python -m jupyter kernelspec remove myenv
```


## Folders in this project 

1. `gopher_call_file_exmples` - folder with example audio files and instructions to teach a technician how to manually listen to audio files for gopher frog calls (without using the RIBBIT model). 
1. `manually_verified_data` - folder with csv files of data from audio files that have been manually listened to for gopher frog calls
1. `python-ribbit` - folder with all code to run RIBBIT model and clean data 


## Using the model 

1. The `ichaway` folder contains all information needed to run the model for data from Ichaway. 
2. The `FLSHE` folder contains all information needed to run the model for data from Fall Line Sandhills East. 
3. Both of the above folders may be easily adapted to alternative datasets by organizing audio files to match the format given within each of those folders. 
4. The `ribbit_functions` folder contains python functions that are used to run the model and organize data. They should not need to be edited for everyday use of the model. 
5. The `gopher_call_examples` folder contains audio file examples of gopher frogs. 


## Current issues

* Some of the file names in the verified Ichaway data have different values for the "minutes" than the actual audio files. This means when merging the verified data with the RIBBIT scores, we either (A) lose some data or we (B) assume the minutes indicator is unimportant. Currently we are using option (A), as it is more reliable, but we do lose some of our data. 


  
  
