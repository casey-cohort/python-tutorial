# Casey lab: Introduction to python
##### January 26, 2026
This is a brief introduction to python. The goal is to facilitate your work where it may be required that you run something in python (e.g., popexposure). This is not a comprehensive training, but rather meant to get you up and running! 

## Outline
1. [Why Python?](#why-should-you-learn-python)
2. [Getting set up](#getting-set-up)
3. [Environments](#environments)
4. [Getting Started with Jupyter Notebooks](#getting-started-with-jupyter-notebooks)
5. [Practice](#practice)
6. [Resources](#resources)

## Why should you learn Python?

- simple, streamlined syntax (e.g., no more lapply!)
- greater versatility
- optimized spatial data processing packages (e.g., `geopandas`, `rasterio`, `shapely`)
- many things will be faster (e.g., intersecting 100 polygons in R takes 10 minutes, in Python it takes <1 second)

## Getting set up 
Let's first make sure everyone has Python and miniconda installed on their laptops. We will be using conda to manage our environments, which we will talk about in a moment.

To do make sure you are all set up, open your terminal and run the following commands:

`conda --version`

1. If you see a version number: 
    You have miniconda installed. Check to make sure you also have python, but it generally comes with miniconda so there should be no issues.

    `python --version`

    If not, you can install it [here](https://docs.anaconda.com/miniconda/).

2. If you do not see a version number: 
    You need to install miniconda. You can do so [here](https://docs.anaconda.com/miniconda/).
    After you install, close and reopen your terminal and run the following commands:

    `conda --version`
    `python --version`

    You should see version numbers for both of these, now. If not, you may need to restart again or you may not have finished installing miniconda. 

## Environments

You should ALWAYS use an environment when you are using python! Installing packages into your base environment WILL lead to version conflicts and WILL create issues in rerunning code in the future. ALWAYS ALWAYS ALWAYS use an environment.

Some specific ways environments can help you:
- ensure reproducibility
- avoid package version conflicts 
- facilitate collaboration
- keep project-specific dependencies separate

### Setting up an environment

Let's open a terminal window and create a new practice environment called `practice_env` with python version 3.10: 

`conda create -n practice_env python=3.10`  
<br>

To activate our practice environment: 

`conda activate practice_env`  
<br>

To deactivate our practice environment: 

`conda deactivate`


### Installing packages in your environment

Now let's set up our environment so we can use it. To do this, we will re-activate it, install some packages, and then start using it! 

To start, let's activate our environment again as we did above: 

`conda activate practice_env`  
<br>
Now let's install some packages. We will install `pandas`, `geopandas`, `jupyterlab`, `matplotlib`, `contextily`, `scipy`, and `numpy`. After each `pip install` line, hit enter and then do the next one.

`pip install pandas`  

`pip install geopandas`  

`pip install jupyterlab`  

`pip install matplotlib`  

`pip install contextily`   

`pip install scipy`

`pip install numpy`

<br>

Now we should be good! If we need other packages, we can always install them using this same method. You can use `pip install` anytime, just sure your environment is activated when you do! If you forget to activate your environment, you will install the package into your base environment...which we do not want! 

## Getting Started with Jupyter Notebooks

We will use Jupyter notebooks to run our code. Jupyter notebooks are a great way to write and run code interactively. They are also a great way to share code with others. We can create a new notebook by clicking the "new file" button on the left sidebar and writing a filename with a .ipynb extension.

We can activate our environment by opening a new terminal window (Terminal > New Terminal) and typing `conda activate practice_env`. For today, though, we will use the existing notebooks I have created for you.

## 1. Python to R
Open the `01_python_to_r/python_to_r.Rmd` file. This R Markdown file contains Python code that we will translate to R.

## 2. Python Basics
Open the `02_python_practice/python_practice.ipynb` notebook. This notebook contains Python code that we will practice.

## 3. Spatial Data
Open the `03_python_spatial/spatial_data.ipynb` notebook. This notebook contains Python code that we will practice with spatial data.