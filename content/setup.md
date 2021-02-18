---
 layout: default
 title: Setting up your system with Python & Anaconda
 parent: Outline
 nav_order: 15
---

# Setting up your system with Python & Anaconda

Anaconda is an open source tool for organizing and setting up your Python environment. It handles dependencies, organizes Python libraries, and allows you to have multiple instances of Python set up on your machine without trouble.

<a href="https://www.anaconda.com/products/individual"><button>Install Anaconda Navigator</button></a>

Get started with Conda

## Getting started with Conda from Navigator
Open navigator and go to "Environments".
![Anaconda Navigator first screen](content/images/anaconda-navigator.png)

Create a new environment by selecting "create".
![Anaconda Navigator select environment button](content/images/anaconda-navigator-env.png)

Select the version of Python you want to work with. By default Anaconda selects the most recent version, in this case Python 3.8 which is fine for this workshop. Choose a short, descriptive name with no spaces or use
![Anaconda Navigator choose type of python](content/images/anaconda-navigator-env-choose-python.png)

You should see your new environment in the left hand column. Clicking on the name of the environment activates the environment which is indicated by a green triangle or "play" button.
![Anaconda Navigator activate environment](content/images/anaconda-navigator-myenv-activate.png)

All Python libraries that are currently in the environment are listed on the right hand side.
![Anaconda Navigator list of packages on right hand side of screen](content/images/anaconda-navigator-myenv-packages.png)

To start using your new environment, click on the green "play" button and select "open in terminal".
![Anaconda Navigator open in terminal](content/images/anaconda-navigator-myenv-terminal.png)

### Using Anaconda without Navigator

To get started with Python we need to create a new Anaconda environment using the “conda” command. This calls on Anaconda to make a new bucket with the correct environment variables for a given version of python.

The base command is as follows where “myenv” is the name of your new environment.

Input
{: .label .label-green}
~~~
conda create -n myenv
~~~

And if you want to specify a specific version of python you can add it after the base command.

Input
{: .label .label-green}
~~~
conda create -n myenv python=3.6
~~~

Once created you need to activate the environment to use it.

Let’s say you’ve made several environments and want to double check or delete what you’ve done.

Input
{: .label .label-green}
~~~
conda info --envs
~~~

Activate conda environment

Input
{: .label .label-green}
~~~
conda activate myenv
~~~

and check it is correctly set up.

Input
{: .label .label-green}
~~~
conda env --list
~~~

More on conda commands and environment management here: https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#updating-an-environment
{.note}

## Installing Python libraries
Generally the easiest way to install Python libraries is using “pip” which is a command line tool. To begin with we need to install NLTK (Natural Language ToolKit) using pip.

Input
{: .label .label-green}
~~~
pip install nltk
~~~

More on pip...
{.note}

Then we can call on nltk and install the rest of the pieces by “importing” nltk and downloading the vader lexicon (a dataset that determines semantic ranking for different terms) and punkt which is a tokenizer

Open a file in a text editor and type:
~~~
import nltk
nltk.download('vader_lexicon')
nltk.download('punkt')
~~~

Explore VADER lexicon: https://www.kaggle.com/nltkdata/vader-lexicon
{.note}

Once you’ve taken these steps you are ready to run Vader commands.

Check NLTK setup

Check version of python
Input
{: .label .label-green}
~~~
~~~

Check version of NLTK

Input
{: .label .label-green}
~~~
~~~

Check version of VADER

Input
{: .label .label-green}
~~~
~~~
