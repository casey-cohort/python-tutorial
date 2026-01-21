# introduction to Python for the Casey Lab
the purpose of this tutorial is to help you get started with Python. 

## why python? 
- similar to r, python is easy to read and write, it is used across research disciplines, and has a lot of powerful packages like `numpy` and `pandas` for data manipulation and analysis.
- often, python is faster than r for certain operations, such as spatial analysis, because: 
    - a lot of the tools in python, such as `numpy` and `pandas`, are written in C and designed for performance at scale. 
    - it is also easier to implement parallel processing in python.
    - for spatial analysis, Python's geopandas, shapely, and rasterio are thin wrappers around these fast C/C++ libraries, with less overhead.
    - memory efficiency — Python handles large rasters and satellite imagery more gracefully
    - Google Earth Engine — the Python API is more developed and better supported than the R equivalent (rgee)

## when to consider switching 
- large datasets
- spatial analysis
- slow r code
- large rasters and satellite imagery
- Google Earth Engine
- parallel processing

## contents

- `practice.Rmd` - R Markdown file with Python code to translate (no answers)
- `practice_with_answers.Rmd` - R Markdown file with answers
- `python_practice.ipynb` - Jupyter notebook for practicing Python basics
- `data.csv` - Sample dataset

---

## python setup

### 1. clone this repository

### 2. install vscode
see [00_vscode_setup.md](00_vscode_setup.md) for instructions.

### 3. why use environments?

**always use a virtual environment** for Python projects. environments isolate your project's dependencies, preventing conflicts between different projects.

### 4. creating and using environments

in your terminal:

```bash
# create a new environment
conda create -n NAME_OF_ENV python=3.10

# activate the environment
conda activate NAME_OF_ENV

# deactivate the environment
conda deactivate
```

### 5. installing packages

- use `pip` for Python packages (most common)
- use `conda` for non-Python dependencies or complex scientific packages

```bash
# activate the environment
conda activate tutorial

# install with pip
pip install package_name

# install with conda
conda install package_name
```

### 6. pre-commit hook
https://pre-commit.com/ ensures that you do not push a jupyter notebook to github with output in it. this is important because you may mistakenly push something that should not be on github, or that is too big to be on github. the pre-commit hook will check for output in your jupyter notebooks. if there is output, it will fail, then it will clear the output, then you can add, commit, and push again.

to set this up: 
1. pip install pre-commit
2. pre-commit install
3. make sure the .pre-commit-config.yaml file is in the root of your repository. you can copy and paste this exact file into each of your repositories.


---

## tutorial exercises

### exercise 1: python to r translation

practice translating Python code to R using the `practice.Rmd` file.

**setup:**

```bash
conda create -n tutorial python=3.10
conda activate tutorial
pip install pandas numpy scipy tabulate
```

**instructions:**

1. open `practice.Rmd` in VSCode or RStudio
2. read through the Python code
3. write the equivalent R code in the empty chunk
4. check your work against `practice_with_answers.Rmd`

### exercise 2: python basics notebook

practice python fundamentals with the jupyter notebook.

**instructions:**

1. make sure your environment is activated: `conda activate tutorial`
2. open `python_practice.ipynb` in VSCode
3. work through the exercises, running each cell with Shift+Enter
4. complete the practice problems at the end

---

## quick reference: python vs r

| task | python (pandas) | r (tidyverse) |
|------|-----------------|---------------|
| read CSV | `pd.read_csv("file.csv")` | `read_csv("file.csv")` |
| view head | `df.head()` | `head(df)` |
| column mean | `df['col'].mean()` | `mean(df$col)` |
| filter rows | `df[df['col'] > 5]` | `filter(df, col > 5)` |
| select columns | `df[['a', 'b']]` | `select(df, a, b)` |
| rename column | `df.rename(columns={'old': 'new'})` | `rename(df, new = old)` |
| new column | `df['new'] = df['a'] + df['b']` | `mutate(df, new = a + b)` |

---

## tips

- **indentation matters in Python!** use 4 spaces (not tabs) for code blocks
- **0-indexed:** python counts from 0, R counts from 1
- **assignment:** Python uses `=`, R uses `<-` (though `=` also works)
- **use `print()`:** unlike R, Python won't automatically display results in scripts

---

## troubleshooting

**"module not found" error:**
```bash
pip install module_name
```

**conda environment issues:**
```bash
conda deactivate
conda activate tutorial
```

**jupyter can't find kernel:**
```bash
pip install ipykernel
python -m ipykernel install --user --name=tutorial
```
