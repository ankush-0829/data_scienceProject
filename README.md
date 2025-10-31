TerraWing - UAVs in the agricultural sector
TerraWing is a service for recognizing and classifying obstacles in the path of UAVs. Our solution is designed for use in the agricultural sector.

Uniqueness
System performance
The project has reached the MVP stage.
Usage
Development prospects
Specialized dataset
AI plugins embedded on the server to enable work with various tasks
Automatically generates a drone's workspace map
Joint operation of several UAVs
Integration with weather services.
Getting Started
Let's install pyenv for easy Python version management.
Windows Chocolatey:choco install pyenv-win
Linux/macOS:curl https://pyenv.run | bash
Viewing available Python versions in pyenv: pyenv install --list Install Python 3.11 or later:pyenv install 3.11.8

Installing the poetry package manager
Windows Powershell:(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | py -
Linux/macOS:curl -sSL https://install.python-poetry.org | python3 -
Virtual environment
If you are using pyenv run the following commands:

poetry config virtualenvs.prefer-active-python true
pyenv local <python version number, in our case 3.11.8>


Preparing a virtual environment for poetry:

poetry use env <python version number, in our case 3.11.8>


Entering the virtual environment

poetry shell


Installing dependencies:

poetry install


Copy the settings file template:

Windows:

copy .env.dist .env


Linux/macOS:

cp .env.dist .env


We edit our settings in .env...

Starting the server
We execute the commandpython app.py

Dev
Help with development
To launch Linter ruff
use the following commandpoetry run ruff check src
Code formatting black
To run, use the following command:poetry run black src
Server tests
In the folder testsyou can find the file test_video_stream.py This file gives us the ability to emulate a drone by sending any video file as a video stream to the server, or broadcasting our webcam.

To launch the client with a pre-prepared video broadcast, use this command: python test_video_stream.py <drone_id> <drone_secret>

Note

If you want to broadcast your webcam, just remove the argumentvideo_source

Model training
Link to the dataset: https://www.kaggle.com/datasets/dimflix/obstacles-in-flight-for-drones
Along the way, src/neural_networkyou can find the file TrainNeuralNetwork.ipynb. This is used to train the neural network.

Note

The dataset must be located in the foldersrc/data/DATASET

Warning

If you use Pycharm and file indexing, we recommend adding the dataset folder to the excluded list. You can do this by right-clicking the folder and selecting Mark Directory as. Then, select excluded.
