# Voice input classification using Audio Spectrogram Transformer
Classifying voice recordings of MEGA Silk Way boutique names. For example, a person pronounces 'Zara', and the model must recognize the boutique name.

## Data
Self-recorded 5406 audio samples for 262 boutiques in MEGA Silk Way, Astana, Kazakhstan. Recorded by me, Anuar Kengesbek, Dias Daurenuly and Dias Rysbekov.

## Model
Pre-trained Audio Spectrogram Transformer (AST) from Huggingface was used to classify the audios into 262 classes (boutique names). Models smaller than 'base384' variant were not able to learn on the data. In the current version of the notebook, there is a unneccessary usage of large length parameter for audios, slowing the training and inference (1024, whereas ~256 would have sufficed considering the duration of audio recordings in the dataset). [Notebook with code](https://github.com/luftpro/mega-name-recognition/blob/main/mall-audio-rec.ipynb)

## Methodology
Data augmentation in the form of time- and frequency-masking was applied actively to compensate for a relatively small dataset. Training was monitored through [Weights & Biases](https://wandb.ai/).

## Results
The model achieved the accuracy of 94% and f1-score of **0.94** on the validation set.
