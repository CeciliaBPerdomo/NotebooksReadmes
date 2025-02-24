# 📒 Notebooks: A Single Workspace
## 📌 What is a Notebook and How Does It Work?
A **notebook** (like Jupyter Notebook or Google Colab) is an interactive environment where you can write and execute code in **cells**.

Unlike traditional code files (`.py` in Python, for example), where all the code runs from top to bottom in a single file, in a notebook **you can run different parts of the code at different times and in any order**.

However, all cells share the same **memory** and the same **state**.

## 🔹 Imports and Variables in Notebooks
When you run a cell in a notebook, the code inside that cell **executes and is stored in memory**. This means that if you define a variable or import a library in one cell, you can use it in another cell without needing to repeat the import or definition.

### ✍ Example of Imports
In one cell, we can import a library like `math`:
``` python
import math  # We import the math library
``` 

Then, in a different cell, we can use `math.sqrt()`, even if we haven't rewritten `import math`:
``` python
print(math.sqrt(25))  # Works because math is already imported in memory
``` 

## ❌ Common Error: Running Cells in the Wrong Order
If we try to use something before running it, we will get an error.
### 🔻 Typical Error:
``` python
print(math.sqrt(25))  # ERROR: math is not imported yet
``` 

### 🔺 Solution
First, run the cell where we import `math`, then run the cell with `print(math.sqrt(25))`.

### 💡 Key Rule
The code you run in a cell becomes available throughout the notebook, but only after you run it.

## 🛠 Step-by-Step Exercise
Follow these steps to better understand how the notebook works:

1️⃣ In the first cell, import the `random` library:
``` python
import random
``` 

2️⃣ In the second cell, generate a random number using `random.randint(1, 10)`:
``` python
number = random.randint(1, 10)
print("Random number:", number)
```

3️⃣ Run the second cell without running the first one. What happens?

4️⃣ Now run the first cell and then run the second one again.

### ✅ Conclusion:
- If you run a cell with an import or a variable, it is stored in the notebook's memory.
- You can use what you defined in any other cell, as long as you have run the cell that defined it first.
- If you close the notebook or restart the kernel, you will lose everything that was in memory and will have to run the necessary cells again.

**📌 Final Summary: A notebook is a single workspace where all cells share memory, but you must run them in the correct order for them to work properly. 🚀**


# 🎓 Google Colab: Limited Resources and Alternatives
## 📌 What is Google Colab?
Google Colab (or Google Colaboratory) is a cloud-based notebook environment that allows you to run Python code without installing anything on your computer. It is ideal for learning, experimenting, and doing small to medium projects with **free access to GPUs and TPUs**.

However, **Colab has limited resources**, which means that:

✔ You cannot use the full power of a supercomputer.

✔ The runtime of the machines is limited.

✔ It can automatically disconnect you if you are inactive or consume too much memory.

## 🔴 Limitations of Google Colab
1️⃣ Limited RAM and CPU
- In the free version, you get around 12 GB of RAM and a moderate virtual CPU.
- If you consume too much memory, the notebook can restart and you will lose everything that was not saved.

2️⃣ Maximum Runtime
- Sessions in Google Colab are not permanent.
- If you stop using the notebook for a while or run long processes, Google can automatically close it.

3️⃣ Restricted Access to GPU and TPU
- You can use a GPU to speed up calculations with TensorFlow or PyTorch, but it is not guaranteed that you will always have access.
- If many people are using Colab at the same time, you might not get an available GPU.

To see if you have GPU enabled, use this command in a cell:

``` python
!nvidia-smi
```

4️⃣ Data Loss if the Environment is Restarted
- If the environment disconnects or restarts, everything that was in memory (variables, models, temporary files) **is lost**.
- To avoid this, **save your important files to Google Drive or download them to your machine**.

## ✅ Solutions and Alternatives
🔹 Save Files to Google Drive
To avoid losing files when Colab restarts, you can connect it to your Google Drive:
``` python
from google.colab import drive
drive.mount('/content/drive')
```

🔹 Work on Your Own Computer
If you need more resources or unlimited time, consider installing Jupyter Notebook or using a local environment like **Anaconda**.

📌 Steps to install Jupyter Notebook on your PC:

    1️⃣ Download and install Anaconda from https://www.anaconda.com/.

    2️⃣ Open Anaconda and run:

``` python
jupyter notebook
```

    3️⃣ Your browser will open with an environment similar to Google Colab, but using your **PC's resources**.

🔹 **Google Colab Pro** (Optional, but Paid)

If you need more RAM or guaranteed access to GPUs, Google offers **Colab Pro** (paid), which gives you better resources and more runtime.

## 🔥 Conclusion
**💡 Google Colab is excellent for quick tests and small projects, but if you need more computing power, it is best to work on your own computer or on more powerful servers. 🚀**



# 📝 VS Code Notebooks: Interactive Programming on Your Computer

## 📌 What is a Notebook in VS Code?
A **VS Code Notebook** is a special type of file (`.ipynb`) that allows you to run code in **cells**, similar to Jupyter Notebook or Google Colab. The main difference is that **everything runs on your own computer**, which means you have full control over resources and runtime.

✅ Advantages of using notebooks in VS Code:
- You can run code in individual cells without running the entire script.
- You do not depend on the internet or Google Colab.
- You can use all the power of your computer (more RAM, CPU, and GPU if you have one).
- It integrates with Python and Jupyter extensions in VS Code.

## 🛠 How to Use Notebooks in VS Code

### 🔹 1. Installation Requirements
To use notebooks in VS Code, you need to install some tools:

1️⃣ Install VS Code
- Download it from https://code.visualstudio.com/

2️⃣ Install the Python Extension
- Open VS Code
- Go to the Extensions tab (Ctrl + Shift + X)
- Search for Python and install it.

3️⃣ Install Jupyter in Python
- If you do not have it installed, open a terminal in VS Code and run:
``` python
pip install jupyter
```

### 🔹 2. Creating a Notebook in VS Code

1️⃣ Open VS Code.

2️⃣ Go to File > New File and save the file with the .ipynb extension.

3️⃣ You will see an environment similar to Jupyter with code cells.

4️⃣ Write code in a cell and run it with the ▶️ button or by pressing Shift + Enter.

🖥 Basic Example in VS Code Notebooks

🔹 Cell 1: Import Libraries
``` python
import math
```

🔹 Cell 2: Use the imported library
``` python
print(math.sqrt(36))  # Output: 6.0
```

💡 **Remember**: Just like in Jupyter or Colab, cells share memory, so you can define a variable in one cell and use it in another.

## ⚡ Key Differences between VS Code Notebooks and Google Colab
| Feature             | VS Code Notebooks 🖥       | Google Colab ☁️          |
|---------------------|----------------------------|--------------------------|
| Location            | Local computer             | Google cloud             |
| Resources           | Unlimited, depends on your PC | Limited                 |
| Internet Connection | Not necessary              | Necessary                |
| GPU Access          | If you have a GPU, you can use it with CUDA | Depends on availability |
| Runtime             | Unlimited                  | Can disconnect           |


## 🎯 Conclusion
📌 **VS Code Notebooks give you more control over your resources and do not have the limitations of the cloud**. If you work on large projects or need more power, it is a better option than Google Colab.

✅ **Recommendation**: If you are going to work with notebooks in the long term, install **VS Code and Jupyter** on your computer to avoid the restrictions of Google Colab. 🚀
