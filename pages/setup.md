## Setup Instructions
Below are detailed instructions to setup a working environment for the workshop materials and associated suggested workflow. Ultimately it is up to you which method you prefer and experienced students may want to create their own environment and workflows tailored to their preferences.

It is suggested you setup your environment after you are a member of the "mlp-s2-22" organisation. This will give you access to all the materials needed for the course. To do this make sure to fill out the [Getting to Know You](example.com) survey so I have the required details for setup (e.g. GitHub Username).

### Cloud Setup
We recommend the use of Google Colab as a cloud environment for running, working, and submitting code for this course. This is because it...

- Provides an easy setup for the working environment.
- Guarentees space to hold the datasets we will use in this course in RAM memory.
- Allows the free use of GPU's for Deep Learning models.

#### Setup

1. Navigate to [http://colab.research.google.com/github](http://colab.research.google.com/github).
2. Click the "Include Private Repos" checkbox.
3. In the popup window, sign-in to your Github account.
4. Make sure "mlp-s2-22" has a green tick next to it under "Organization access" (otherwise request access) and then authorize Colab to read the private files.
5. Your private repositories and notebooks will now be available via the github navigation pane on google colab.

#### Suggested Workflow

1. Navigate to [http://colab.research.google.com/github](http://colab.research.google.com/github).
2. Click the "Include Private Repos" checkbox.
3. Navigate to your workshop repository and open the .ipynb file.
4. Add any code you wish. 
    
    If you are signed into a Google Account you can save a working copy to your Google Drive while you work (Ctrl+S).

5. When you are done working on a section, make sure to save a copy back onto GitHub (File, Save a Copy in GitHub).

> **Warning**: This simple way of saving your work to GitHub does mean you have to be careful you are not about to remove someone elses work from the latest version when working in a team. You will just commit your version of the code to the top of the repository history without any warning if someone else has added to it before you send your copy across. To avoid this if working in a team, you may want to use the local setup (detailed below), a combined approach, or ensure only one of you works on the code at any one time.

---

### Local Setup<sup>1</sup>
You may instead want to work on this project on your own machine using this suggested local setup and workflow.

#### Setup

1. __Install Python 3 and Libraries__

    We suggest you [download and install Anaconda](https://www.anaconda.com/distribution/), which comes bundled with most of the required libraries. If you prefer a lighter weight Anaconda distribution, you can [install Miniconda](https://docs.conda.io/en/latest/miniconda.html).
  
    - During the installation on MacOSX and Linux, you will be asked whether to initialize Anaconda by running `conda init`: you should accept, as it will update your shell script to ensure that `conda` is available whenever you open a terminal. After the installation, you must close your terminal and open a new one for the changes to take effect.
  
    - During the installation on Windows, you will be asked whether you want the installer to update the `PATH` environment variable. This is not recommended as it may interfere with other software. Instead, after the installation you should open the Start Menu and launch an Anaconda Shell whenever you want to use Anaconda.
  
    > **Note**: if you don't like Anaconda for some reason, then you can install Python 3 and use pip to install the required libraries manually (this is not recommended, unless you really know what you are doing).

2. __Install the GPU Driver and Libraries (Optional)__

    If you have a TensorFlow-compatible GPU card (NVidia card with Compute Capability ≥ 3.5), and you want TensorFlow to use it, then you should download the latest driver for your card from [nvidia.com](https://www.nvidia.com/Download/index.aspx?lang=en-us) and install it. You will also need NVidia's CUDA and cuDNN libraries, but the good news is that they will be installed automatically when you install the `tensorflow-gpu` package from Anaconda. However, if you don't use Anaconda, you will have to install them manually. If you hit any roadblock, see TensorFlow's [GPU installation instructions](https://tensorflow.org/install/gpu) for more details.

3. __Clone the local setup repository (`mlp-env`)__

    If required, make sure to download and install git from [git-scm.com](git-scm.com).
    
    Clone the local setup repository (`mlp-env`) by opening a terminal and typing the following commands:
    ```
    $ cd $HOME  # or any other development directory you prefer
    $ git clone https://github.com/mlp-s2-22/mlp-env
    ```
    You could instead use the Github Desktop GUI by navigating to the mlp-env repository webpage (https://github.com/mlp-s2-22/mlp-env), click the green "Code" button, and "Open with GitHub Desktop".

4. __Create an `mlp` environment__

    Using your Terminal (MacOSX and Linux) or Anaconda Shell (Windows) navigate to the `mlp-env` directory.

    Run the following command to create a new `conda` environment containing every library you will need to run all the notebooks (by default, the environment will be named `mlp`, but you can choose another name using the `-n` option):
    ```
    $ cd mlp-env
    $ conda env create -f environment.yml
    ```

#### Suggested Workflow

1. __Get a local version of your teams workshop repository__

    If this is the first time you are working locally on the repository then you need to `clone` it. For example, to clone your repository (e.g. https://github.com/mlp-s2-22/w01-workshop-teamname) to your local machine, you could open a terminal and type the following commands:
    ```
    $ cd $HOME  # or any other directory you prefer
    $ git clone https://github.com/mlp-s2-22/w01-workshop-teamname
    ```
    
    You could instead use the Github Desktop GUI by navigating to your teams workshop repository webpage, click the green "Code" button, and "Open with GitHub Desktop".

2. __Run a Jupyter Notebook__
    
    You could open a Terminal (MacOSX and Linux) or Anaconda Shell (Windows), and run:
    ```
    $ conda activate mlp
    $ jupyter notebook
    ```
    This should open up your browser, and you should see Jupyter's tree view, with the contents of the current directory. If your browser does not open automatically, visit [localhost:8888](http://localhost:8888/tree). When you're done with Jupyter, you can close it by typing Ctrl-C in the Terminal window where you started it.

    If using the Anaconda Navigator GUI, on the "Home" tab make sure your "Applications on mlp" by using the dropdown box to ensure the environment is activated. Then "Launch" the Jupyter Notebook.

3. __Save changes to Git and GitHub__

    After you make any changes that you want to save to your local git history, you should first `add` these files that have been changed to the git staging area and then `commit` them. 

    If your using the Terminal for git, you could use the following code (provided your current directory is your local repository):
    ```
    $ git add -p
    $ git commit
    ```
    If you are using GitHub Desktop, then any changes are already added for you in the left panel, you just need to write a commit message in the "Summary" box and press the "commit" button when you want to save them.

    You probably want to store these on the remote GitHub where your teammates and tutors can see them. But before doing anything else its worth trying to `pull` any new changes. This is to avoid any merge conflicts if other teammates have been working on the code. If anything conflicts with your code, you need to manually make these fixes. Then you are ready to `push` your code. 

    If you are using the Terminal for git, you could you could use the following code:
     ```
    $ git pull
    $ git push
    ```

    If you are using GitHub Desktop, then you want to first press the "Fetch origin" button in the top right first and pull any changes if made. Then you can press the same button to push. GitHub Desktop will generally be quite helpful if there are conflicts (or you forgot to pull before pushing) but you will likely still need to go into change merge conflicts from time-to-time.

    > **Note**: Keeping an upto date git history that is regularly pushed to GitHub will ensure that merge conflicts are reduced and you don't forget to submit your work on time!

#### Updating Libraries
  
During the course I may need to update the `conda` environment to fix issues and add support for new libraries. If you are using a __Local Setup__ you may need update this environment at the start of a workshop. To do this open a Terminal (MacOSX and Linux) or Anaconda Shell (Windows), and run the following:

```
$ cd $HOME    # or whatever development directory you chose earlier
$ cd mlp-env  # go to the environment setup directory
$ git pull    # get the latest dependency files
$ conda update -c defaults -n base conda  # update conda
$ conda activate base       # make sure the environment is not activated
$ conda env remove -n mlp   # delete the current project's environment
$ conda env create -f environment.yml   # create the new environment
```

---
### References 
1. https://github.com/ageron/handson-ml2/blob/master/INSTALL.md