# Automated bioacoustic monitoring tool for gopher frogs (Lithobates capito)

## Summary

This project uses the [repeat interval-based bioacoustic identification tool (RIBBIT)](https://conbio.onlinelibrary.wiley.com/doi/epdf/10.1111/cobi.13718) from [OpenSoundscape](http://opensoundscape.org/en/latest/) to identify gopher frog calls in audio recording. The goal is to create a tool that can be used by conservationists to monitor endangered gopher frog populations and devise management plans. 

## Instalation and setup 

1. Install OpenSoundscape as directed [here](http://opensoundscape.org/en/latest/). 
1. If you are unfamiliar with Python environments, use the `python_ribbit/create_environment.ipynb` file to guide you through creating an OpenSoundscape environment. 


## Folders in this project 

1. `gopher_call_file_exmples` - folder with example audio files and instructions to teach a technician how to manually listen to audio files for gopher frog calls (without using the RIBBIT model). 
1. `manually_verified_data` - folder with csv files of data from audio files that have been manually listened to for gopher frog calls
1. `python-ribbit` - folder with all code to run RIBBIT model and clean data 


## Using the model 

1. Use the `run_lcapito_model.ipynb` file to run the gopher frog model with new data. 
  * You can adjust the RIBBIT parameter values and/or what files you want to run through the model - all parameters that are intended to be "editable" by users are indicated with `#*#` 
  * Directions/tips on using the model are given within the file 
  * Two examples of using the model are given. The only difference is the structure of the directories that contain the audio files. To use it on your own computer/data, you will have to edit the file paths to match where your audio file data is stored. The examples were created to make it easy to run data from our two collaborating sites (Sandhills and Ichaway), but should be easily editable to be used for other sites, as long as the directory structure is similar. The key to avoiding errors while using this model is making sure your file paths are accurate. 
  * There is also an example of conducting a one-factor-at-a-time parameter exploration if you want to try to improve the model's paramters. 

1. The data cleaning files are two examples of how to combine the RIBBIT score csv files with data of files that have already been manually listened to, to assess the capabilities of the model (e.g. precision and recall). 

1. The `eda.ipynb` file is an example of exploratory data analysis using the cleaned data. 

## Current issues

* Some of the file names in the verified Ichaway data have different values for the "minutes" than the actual audio files. This means when merging the verified data with the RIBBIT scores, we either (A) lose some data or we (B) assume the minutes indicator is unimportant. Currently we are using option (A), as it is more reliable, but we do lose some of our data. 


  
  