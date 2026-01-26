# introduction to Python for the Casey Lab
the purpose of this tutorial is to help you get started with Python. 

## when to consider switching 
- large datasets
- spatial analysis
- slow r code
- large rasters and satellite imagery
- Google Earth Engine
- parallel processing

## contents

- `01_python_to_r/python_to_r.Rmd` - R Markdown file with Python code to translate (no answers)
- `01_python_to_r/python_to_r_with_answers.Rmd` - R Markdown file with answers
- `02_python_practice/python_practice.ipynb` - Jupyter notebook for practicing Python basics
- `02_python_practice/python_practice_with_answers.ipynb` - Jupyter notebook with answers to the practice problems
- `03_python_spatial/spatial_data.ipynb` - Jupyter notebook for practicing spatial data analysis

---

## python setup

### 1. clone this repository

### 2. install vscode
see [00_setup/02_vscode_setup.md](00_setup/02_vscode_setup.md) for instructions.

### 3. set up python and environments
see [00_setup/01_python_setup.md](00_setup/01_python_setup.md) for instructions.

### 4. For the future, set up a pre-commit hook
https://pre-commit.com/ ensures that you do not push a jupyter notebook to github with output in it. this is important because you may mistakenly push something that should not be on github, or that is too big to be on github. the pre-commit hook will check for output in your jupyter notebooks. if there is output, it will fail, then it will clear the output, then you can add, commit, and push again.

to set this up: 
1. pip install pre-commit
2. pre-commit install
3. make sure the .pre-commit-config.yaml file is in the root of your repository. you can copy and paste this exact file into each of your repositories.


---

## tutorial exercises

### exercise 1: python to r translation

practice translating Python code to R using the `python_to_r.Rmd` file.

**instructions:**

1. open `01_python_to_r/python_to_r.Rmd` in VSCode
2. read through the Python code
3. write the equivalent R code in the empty chunk
4. check your work against `01_python_to_r/python_to_r_with_answers.Rmd`

### exercise 2: python basics notebook

practice python fundamentals with the jupyter notebook.

**instructions:**

1. make sure your environment is activated: `conda activate practice_env`
2. open `02_python_practice/python_practice.ipynb` in VSCode
3. work through the exercises, running each cell with Shift+Enter
4. complete the practice problems at the end

### exercise 3: spatial data analysis

practice spatial data analysis with the jupyter notebook.

**instructions:**

1. make sure your environment is activated: `conda activate practice_env`
2. open `03_python_spatial/spatial_data.ipynb` in VSCode
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
conda activate practice_env
```

**jupyter can't find kernel:**
```bash
pip install ipykernel
python -m ipykernel install --user --name=practice_env
```
