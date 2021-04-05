TF Speech Recognition Challenge
Tensorflow Speech Recognition Challenge was a Kaggle competition organised by Google Brain to use the Speech Commands Dataset to build an algorithm that understands simple spoken commands. https://www.kaggle.com/c/tensorflow-speech-recognition-challenge


Project Structure
data
raw
train (Training audio files)
test (Test audio files used for evaluation
libs
classification (All scripts used for training and evaluation)
notebooks
scripts (Executable scripts)
models (Pretrained Models)
Requirements
Tensorflow 1.4
librosa
scikit-learn
Python 3.x
Running
Download the Speech Commands Dataset and extract the dataset in the train folder. Test Audio can be placed in data/test/audio folder.

The notebooks can be run individually using Jupyter. To run the scripts from command line edit the notebooks using Jupyter and run:

./script/execute_notebook.py
and select the notebook to run. The results are stored in results/notebook_name.log

P0 Predict Test WAV.ipynb can be used to predict audio files using a trained graphdef model.

Architecture
Models used
A variant of Convolutional LSTM (https://arxiv.org/pdf/1610.00277.pdf)
LSTM-L (https://arxiv.org/pdf/1711.07128.pdf)
C-RNN (https://arxiv.org/pdf/1711.07128.pdf)
GRU-L (https://arxiv.org/pdf/1711.07128.pdf)
Resnet
Training
The model was trained using a GCP instance with the following specifications:

NVIDIA Tesla P100 X 1
16 GB RAM
35 GB SSD
Most of the models converged in 30k steps. Pseudo Labelling on test data was used to improve the model performance.

Prediction
The final model was a ensemble 13 models. Weighted Averaging and Stacking was used to generate the final predictions.

Aknowledgements
ML-KWS-for-MCU (https://github.com/ARM-software/ML-KWS-for-MCU)
Very Deep Convolutional Neural Network for Robust Speech Recognition (https://arxiv.org/pdf/1610.00277.pdf)
Speech Commands Dataset (https://research.googleblog.com/2017/08/launching-speech-commands-dataset.html)
