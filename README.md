# Gaze Estimation with Deep Learning

This project implements a deep learning model to predict eye region landmarks and gaze direction.
The model is trained on a set of computer generated eye images synthesized with UnityEyes [1]. This work is heavily based on [2] but with some key modifications. 
This model achieves ~14% mean angular error on the MPIIGaze evaluation set after training on UnityEyes alone.

### Setup

NOTE: This repo has been tested only on Ubuntu 16.04 and MacOS. 

First, create a conda env for your system and activate it:
```bash
conda env create -f env-linux.yml
conda activate ge-linux
```

Then download the pretrained model files. One is for detecting face landmarks. The other is the main pytorch model.

```bash
./scripts/fetch_models.sh
```

Finally, run the webcam demo. You will likely need a GPU and have cuda 10.1 installed in order to get acceptable performance. 

```bash
python run_with_webcam.py
```

If you'd like to train the model yourself, please see the readme under `datasets/UnityEyes`.

### References

1. https://www.cl.cam.ac.uk/research/rainbow/projects/unityeyes/
2. https://github.com/swook/GazeML
3. https://github.com/princeton-vl/pytorch_stacked_hourglass
