# Epic Day: Music

## Steps
1. Downloading music to be analyzed with fma:

```
$ curl -O https://os.unil.cloud.switch.ch/fma/fma_small.zip
$ unzip fma_small.zip
```

2. Downloading the DeepAudioClassification repo and setting it up

```
$ git clone https://github.com/despoisj/DeepAudioClassification.git
$ cd DeepAudioClassification
$ virtualenv virtualenv
$ source virtualenv/bin/activate
$ pip install -r pip-requirements.txt
$ pip install tensorflow
$ mkdir Data
$ mkdir Data/Raw
$ mv ../fma_a_dataset_for_music_analysis/fma_small/**/*.mp3 Data/Raw/
$ sudo apt-get install sox libmagic-dev libsox-fmt-mp3
$ python main.py slice
$ pyhton main.py train #failing!
```

3. Launching it in Docker
```
$ docker build .
$ docker run --name deep-audio-classification -p 6006:6006 -d {imageID}
$ docker cp ../DeepAudioClassification/. deep-audio-classification:/notebooks
$
```
















## Python's virtual environment commands:

```
$ virtualenv {name} #Create a virtualenv in the current directory
$ source {name}/bin/activate #Activate a virtualenv
$ pip list #List the packages installed (in the actived virtualenv)
$ pip install -r {file} #Install the packages listed in the file
$ deactivate #Deactivate the virtualenv
```

