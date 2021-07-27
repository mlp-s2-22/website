## Setup Instructions
Below are detailed instructions to setup a working environment for the workshop materials and associated suggested workflow. Ultimately it is up to you which method you prefer and experienced students may want to create their own environment and workflows tailored to their preferences.

It is suggested you setup your environment after you are a member of the "mlp-s2-22" organisation. This will give you access to all the materials needed for the course. To do this make sure to fill out the [Getting to Know You](example.com) survey so I have the required details for setup (e.g. GitHub Username).

### Cloud Setup
We recommend the use of Google Colab as a cloud environment for running, working, and submitting code for this course. This is because it...

- Guarentees space to hold the datasets we will use in this course in RAM memory.
- Allows the use of GPU's for Deep Learning models.
- Provides an easy to setup working environment.

#### Setup

1. Navigate to [http://colab.research.google.com/github](http://colab.research.google.com/github).
2. Click the "Include Private Repos" checkbox.
3. In the popup window, sign-in to your Github account.
4. Make sure "mlp-s2-22" has a green tick next to it under "Organization access" (otherwise request access) and then authorize Colab to read the private files.
5. Your private repositories and notebooks will now be available via the github navigation pane.

#### Suggested Workflow

1. Navigate to [http://colab.research.google.com/github](http://colab.research.google.com/github).
2. Click the "Include Private Repos" checkbox.
3. Navigate to your workshop repository and open the .ipynb file.
4. Add any code you wish. 
5. If you are signed into a Google Account you can save a copy to your Google Drive while you work (Ctrl+S).
6. When you are done working on a section, make sure to save a copy back onto GitHub (File, Save a Copy in GitHub).

---

### Local Setup<sup>1</sup>
You may instead want to work on this project on your own machine using this suggested local setup.

#### Setup

1. Download and install git from [git-scm.com](git-scm.com).
- Clone the local setup repository ([TODO INSERT]) by opening a terminal and typing the following commands:
```
$ cd $HOME  # or any other development directory you prefer
$ git clone https://github.com/ageron/handson-ml2.git
$ cd handson-ml2
```
or use the GUI by...

2. Install Python 3 and a bunch of Python libraries.
- We suggest you [download and install Anaconda](https://www.anaconda.com/distribution/), which comes bundled with most of the required libraries. If you prefer a lighter weight Anaconda distribution, you can [install Miniconda](https://docs.conda.io/en/latest/miniconda.html).
  - During the installation on MacOSX and Linux, you will be asked whether to initialize Anaconda by running `conda init`: you should accept, as it will update your shell script to ensure that `conda` is available whenever you open a terminal. After the installation, you must close your terminal and open a new one for the changes to take effect.
  - During the installation on Windows, you will be asked whether you want the installer to update the `PATH` environment variable. This is not recommended as it may interfere with other software. Instead, after the installation you should open the Start Menu and launch an Anaconda Shell whenever you want to use Anaconda.
  > **Note**: if you don't like Anaconda for some reason, then you can install Python 3 and use pip to install the required libraries manually (this is not recommended, unless you really know what you are doing).

3. Install the GPU Driver and Libraries (Optional)
- If you have a TensorFlow-compatible GPU card (NVidia card with Compute Capability ≥ 3.5), and you want TensorFlow to use it, then you should download the latest driver for your card from [nvidia.com](https://www.nvidia.com/Download/index.aspx?lang=en-us) and install it. You will also need NVidia's CUDA and cuDNN libraries, but the good news is that they will be installed automatically when you install the tensorflow-gpu package from Anaconda. However, if you don't use Anaconda, you will have to install them manually. If you hit any roadblock, see TensorFlow's [GPU installation instructions](https://tensorflow.org/install/gpu) for more details.

4. Create an `mlp` Environment 
- Using your Terminal (MacOSX and Linux) or Anaconda Shell (Windows) navigate to the `mlp-s2-22` directory.
- Run the following command to create a new `conda` environment containing every library you will need to run all the notebooks (by default, the environment will be named `mlp`, but you can choose another name using the `-n` option):
```
$ conda env create -f environment.yml
```

- Activate the new environment:
  ```
  $ conda activate mlp
  ```

5. Start Jupyter 
- You just need to register the `mlp` conda environment to Jupyter. The notebooks in this project will default to the environment named `python3`, so it's best to register this environment using the name `python3` (if you prefer to use another name, you will have to select it in the "Kernel > Change kernel..." menu in Jupyter every time you open a notebook):
  ```
  $ python3 -m ipykernel install --user --name=python3
  ```

- You can now start Jupyter like this:
  ```
  $ jupyter notebook
  ```

  This should open up your browser, and you should see Jupyter's tree view, with the contents of the current directory. If your browser does not open automatically, visit [localhost:8888](http://localhost:8888/tree).

- When you're done with Jupyter, you can close it by typing Ctrl-C in the Terminal window where you started it.

TODO: on the website setup the directory for creating the anaconda environment.

#### Suggested Workflow

1. Pull your teams workshop repository (e.g. https://github.com/mlp-s2-22/w01-workshop-teamname) to your local machine by... 

  - opening a terminal and typing the following commands:
  ```
  $ cd $HOME  # or any other directory you prefer
  $ git pull https://github.com/mlp-s2-22/w01-workshop-teamname
  ```
  - using the Github Desktop GUI by navigating to your teams workshop repository, click the green "Code" button, and "Open with GitHub Desktop"

2. Run a jupyter notebook by...
  - opening a Terminal (MacOSX and Linux) or Anaconda Shell (Windows), and running:
  ```
  $ cd $HOME # or whatever development directory you chose earlier
  $ cd mlp-s2-22
  $ conda activate mlp
  $ jupyter notebook`
  ```
---
### References 
1. https://github.com/ageron/handson-ml2/edit/master/INSTALL.md