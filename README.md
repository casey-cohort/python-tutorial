# Introduction to Python for the Casey Lab
The purpose of this tutorial is to help you get started with Python. 

## Contents

- `practice.Rmd` - R Markdown file with Python code to translate (no answers)
- `practice_with_answers.Rmd` - R Markdown file with answers
- `python_practice.ipynb` - Jupyter notebook for practicing Python basics
- `data.csv` - Sample dataset

---

## Python Setup

### Why use environments?

**Always use a virtual environment** for Python projects. Environments isolate your project's dependencies, preventing conflicts between different projects.

### Creating and using environments

In your terminal:

```bash
# Create a new environment
conda create -n NAME_OF_ENV python=3.10

# Activate the environment
conda activate NAME_OF_ENV

# Deactivate the environment
conda deactivate
```

### Installing packages

- Use `pip` for Python packages (most common)
- Use `conda` for non-Python dependencies or complex scientific packages

```bash
# Install with pip
pip install package_name

# Install with conda
conda install package_name
```

### pre-commit hook
https://pre-commit.com/ ensures that you do not push a jupyter notebook to github with output in it. this is important because you may mistakenly push something that should not be on github, or that is too big to be on github. the pre-commit hook will check for output in your jupyter notebooks. if there is output, it will fail, then it will clear the output, then you can add, commit, and push again.

to set this up: 
1. pip install pre-commit
2. pre-commit install
3. make sure the .pre-commit-config.yaml file is in the root of your repository. you can copy and paste this exact file into each of your repositories.


---

## tutorial exercises

### exercise 1: python to r translation

Practice translating Python code to R using the `practice.Rmd` file.

**setup:**

```bash
conda create -n tutorial python=3.10
conda activate tutorial
pip install pandas numpy scipy tabulate
```

**instructions:**

1. Open `practice.Rmd` in RStudio
2. Read through the Python code
3. Write the equivalent R code in the empty chunk
4. Check your work against `practice_with_answers.Rmd`

### exercise 2: python basics notebook

Practice Python fundamentals with the Jupyter notebook.

**instructions:**

1. Make sure your environment is activated: `conda activate tutorial`
2. Open `python_practice.ipynb` in VS Code
3. Work through the exercises, running each cell with Shift+Enter
4. Complete the practice problems at the end

---

## quick reference: python vs r

| Task | Python (pandas) | R (tidyverse) |
|------|-----------------|---------------|
| Read CSV | `pd.read_csv("file.csv")` | `read_csv("file.csv")` |
| View head | `df.head()` | `head(df)` |
| Column mean | `df['col'].mean()` | `mean(df$col)` |
| Filter rows | `df[df['col'] > 5]` | `filter(df, col > 5)` |
| Select columns | `df[['a', 'b']]` | `select(df, a, b)` |
| Rename column | `df.rename(columns={'old': 'new'})` | `rename(df, new = old)` |
| New column | `df['new'] = df['a'] + df['b']` | `mutate(df, new = a + b)` |

---

## tips

- **Indentation matters in Python!** Use 4 spaces (not tabs) for code blocks
- **0-indexed:** Python counts from 0, R counts from 1
- **Assignment:** Python uses `=`, R uses `<-` (though `=` also works)
- **Use `print()`:** Unlike R, Python won't automatically display results in scripts

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
