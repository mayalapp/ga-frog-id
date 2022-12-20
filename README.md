# Automated bioacoustic monitoring tool for gopher frogs (Lithobates capito)

## Summary

This project uses the [repeat interval-based bioacoustic identification tool (RIBBIT)](https://conbio.onlinelibrary.wiley.com/doi/epdf/10.1111/cobi.13718) from [OpenSoundscape](http://opensoundscape.org/en/latest/) to identify gopher frog calls in audio recording. The goal is to create a tool that can be used by conservationists to monitor endangered gopher frog populations and devise management plans. 

## Instalation and setup 

1. Install OpenSoundscape as directed [here](http://opensoundscape.org/en/latest/). 
1. If you are unfamiliar with Python environments, use the `python_ribbit/create_environment.ipynb` file to guide you through creating an OpenSoundscape environment. 


## Folders in this project 

1. `gopher_call_file_exmples` - folder with example audio files and instructions to teach a technician how to manually listen to audio files for gopher frog calls (without using the RIBBIT model). 
1. `manually_verifiedd_data` - folder with csv files of data from audio files that have been manually listened to for gopher frog calls
1. `python-ribbit` - folder with all code to run RIBBIT model and clean data 


## Using the model 

1. Use the `run_lcapito_model.ipynb` file to run the gopher frog model with new data. 
  * You can adjust the RIBBIT parameter values and/or what files you want to run through the model - all parameters that are intended to be "editable" by users are indicated with `#*#` 
  * Directions/tips on using the model are given within the file 
  * Two examples are given - with FLSHE data and Ichaway data. They only difference is the structure of the directories that contain the audio files. To use the model for different directory structures, make sure that the file paths are accurate
  
1. The data cleaning files are two examples of how to combine the RIBBIT score csv files with data of files that have already been manually listened to, to assess the capabilities of the model. 

1. The `eda.ipynb` file is an example of exploratory data analysis using the cleaned data. 
  
  