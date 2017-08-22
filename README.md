# DLND-image-classification

This is the git repository for my solution to the Udacity Deep Learning Nanodegree Foundation assignment 2. It implements a convolutional neural network for classifying the CIFAR-10 dataset

## Running (Linux/Mac + git + conda)

If you want to run the notebook on your own (using anaconda)
```shell
    git clone https://github.com/RomelTorres/DLND-Image-Classification.git
    cd DLND-Image-Classification
    # Create a conda environment from the environment.yml file
    conda env create -f environment.yml
    source activate iclassification
    jupyter notebook dlnd_image_classification.ipynb
```

The notebook is also rendered by github, so you can simply  click on the file Your_first_neural_network.ipynb here and you will see my results.


## Running the project on floydhub.com

1. Create an account on [floydhub.com](https://www.floydhub.com) (don't forget to confirm your email). You will automatically receive 100 free GPU hours.

2. Install the `floyd` command on your computer:

        pip install -U floyd-cli

    Do this even if you already installed `floyd-cli` before, just to make sure you have the most recent version (Its pace of development is fast!).

3. Associate the command with your Floyd account:

        floyd login

    (a page with authentication token will open; you will need to copy the token into your terminal)

2. Clone this repository:

        git clone https://github.com/ludwiktrammer/deep-learning.git

    Note: There are couple minor differences between this repository and the original Udacity repository. You can read about them [in README](https://github.com/ludwiktrammer/deep-learning/tree/master/image-classification#how-is-this-repository-different-from-the-original). To follow this instructions you need to use this repository.

3. Enter the folder for the image classification project:

        cd image-classification

4. Initiate a Floyd project:

        floyd init dlnd_image_classification

5. Run the project:

        floyd run --gpu --env tensorflow --mode jupyter --data diSgciLH4WA7HpcHNasP9j

    It will be run on a machine with GPU (`--gpu`), using a Tenserflow environment (`--env tensorflow`), as a Jupyter notebook (`--mode jupyter`), with Floyd's built-in cifar-10 dataset  available (`--data diSgciLH4WA7HpcHNasP9j`).

6. Wait for the Jupyter notebook to become available and then access the URL displayed in the terminal (described as "path to jupyter notebook"). You will see the notebook.

7. Remember to explicitly stop the experiment when you are not using the notebook. As long as it runs (even in the background) it will cost GPU hours. You can stop an experiment in the ["Experiments" section on floyd.com](https://www.floydhub.com/experiments) or using the `floyd stop` command:

        floyd stop ID

    (where ID is the "RUN ID" displayed in the terminal when you run the project; if you lost it you can also find it in the ["Experiments" section on floyd.com](https://www.floydhub.com/experiments))

**Important:** When you run a project it will always start from scratch (i.e. from the state present *locally* on your computer). If you made changes in the remote jupiter notebook during a previous run, the changes will **not** be present in subsequent runs. To make them permanent you need to add the changes to your local project folder. When running the notebook you can download them directly from Jupyter - *File / Download / Notebook*. After downloading it, just replace your local `dlnd_image_classification.ipynb` file with the newly downloaded one.

Alternatively, If you already stoped the experiment, you can still download the file using the `floyd output` command:

    floyd output ID

(where ID is the "RUN ID" displayed in the terminal when you run the project; if you lost it you can also find it in the ["Experiments" section on floyd.com](https://www.floydhub.com/experiments))

Just run the command above, download `dlnd_image_classification.ipynb` and replace your local version with the newly downloaded one.
