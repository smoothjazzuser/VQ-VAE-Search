# VQ-VAE-Search

This repository contains code modified from VQ-VAE to perform audio similarity search. 

## Files:
- 'Music_VQ_VAE.ipynb' is the main notebook for training and testing the model
- 'audio_functions.ipynb' and 'audio_to_mel_spec.ipynb' contain our experiments for dialing in the type of audio preprocessing we wanted to use. They contain code to convert audio datasets to mel spectrograms (we observed a 10x size reduction). Code may need to be altered based on the audio dataset you are using.
- 'png_to_audio.ipynb' contains our final method for converting spectrograms back to audio. 

## Requirements:
- Install torch: follow https://pytorch.org/get-started/locally/ for your system to ensure GPU support
- pip install torch torchvision torchaudio scikit-learn matplotlib librosa joblib tqdm opencv-python scipy pandas plotly imageio ipykernel ipywidgets jupyter notebook 
- python 3
- For unknown reasons, joblib required backend to be set to 'loky' for our AMD machine, and backend = 'multiprocessing' for our Intel machines. If you are getting errors or freezes when converting the dataset, try changing the backend in the 'audio_to_mel_spec.ipynb' file. Also, make sure you are using an appropriate number of workers for your specific machine and ram.

## Dataset
With minimal modificaiton, 'audio_to_mel_spec.ipynb' can be used to convert most audio datasets to mel spectrograms. Adio is clipped to 10 second clips, so audio clips should be longer or at least equal to this. 