# Installing VS Code for Python & R with Jupyter Notebooks

## 1. Install VS Code

1. Go to [code.visualstudio.com](https://code.visualstudio.com)
2. Download the installer for your operating system
3. Run the installer with default settings

---

## 2. Install Python

1. Go to [python.org/downloads](https://python.org/downloads)
2. Download the latest version for your operating system
3. **Important:** During installation, check the box that says **"Add Python to PATH"**
4. Complete the installation with default settings

---

## 4. Install VS Code Extensions

1. Open VS Code
2. Click the **Extensions** icon in the left sidebar (or press `Ctrl+Shift+X` on Windows/Linux, `Cmd+Shift+X` on Mac)
3. Search for and install each of these extensions:

| Extension | Publisher |
|-----------|-----------|
| Python | Microsoft |
| Jupyter | Microsoft |
| R | REditorSupport |

---

## 5. Install the R Kernel for Jupyter

This step allows Jupyter notebooks to run R code.

1. Open a terminal (Command Prompt on Windows, Terminal on Mac/Linux)
2. Type `R` and press Enter to start R
3. Run these commands:

```r
install.packages("IRkernel")
IRkernel::installspec()
```

4. Type `q()` to quit R
5. When asked to save workspace, type `n` and press Enter

---

## 6. Test Your Setup

### Test Python

1. In VS Code, go to **File → New File**
2. Save it as `test.ipynb`
3. When prompted, select the **Python** kernel
4. In the first cell, type:

```python
print("Hello from Python!")
```

5. Press `Shift+Enter` to run the cell

### Test R

1. Create another new file and save it as `test_r.ipynb`
2. Click the kernel selector in the top right corner
3. Select **R** from the list
4. In the first cell, type:

```r
print("Hello from R!")
```

5. Press `Shift+Enter` to run the cell


## 7. Using the R Terminal

Once the R extension is installed, you can open an interactive R terminal directly in VS Code.

### How to Open the R Terminal

**Option 1:** Click the dropdown arrow next to the `+` button in the Terminal panel and select **R Terminal**

**Option 2:** Open the Command Palette (`Cmd+Shift+P` on Mac, `Ctrl+Shift+P` on Windows/Linux) and search for **R: Create R Terminal**

### If the R Terminal Won't Open (Mac)

The R extension needs to know where R is installed on your computer. If the R Terminal doesn't open:

1. Open VS Code Settings (`Cmd + ,`)
2. Search for `r.rterm.mac`
3. Set the path to one of these (try the first one, then the second if it doesn't work):
   - `/usr/local/bin/R`
   - `/Library/Frameworks/R.framework/Resources/bin/R`

### If the R Terminal Won't Open (Windows)

1. Open VS Code Settings (`Ctrl + ,`)
2. Search for `r.rterm.windows`
3. Set the path to your R installation, typically:
   - `C:\Program Files\R\R-4.x.x\bin\R.exe` (replace `4.x.x` with your version number)
