---
layout: page
title: Colab Tutorial
permalink: /notes/colab-tutorial/

---


In this class, we will use [Colab](https://colab.research.google.com/notebooks/intro.ipynb) for the
programming assignments as it provides a free GPU to every google account. Colab is compatible with Jupyter notebook and it lets you write and execute Python
code in your web browser.

Colab provide a Tesla T4 (15079MiB) with 64G disk space for every google account. It allows every to continuously run for 12 hours. 
If you need more than 12 hours, you need to run your code again.
It is like a server with your own space and environment.

#### How to use

Please upload or directly save the assignment folder on your google drive. (For example, /My Drive/cs682/assignment1).

Go to your [google drive](https://drive.google.com/drive/u/0/folders/15pisR92EJzznxLl5uvUX0WcCtin0D73_).
Go to the assignment folder(For example: /cs682/assignment1), double click the .ipynb(For example, svm.ipynb) that you want to execute and choose to open with Google Colaboratory.

You will see a screen like this:
<div class='fig figcenter'>
  <img src='/assets/colab-tutorial/svm.png'>
</div>

Now we show how to activate GPU.

Goto Edit->Notebook Setting and choose GPU:
<div class='fig figcenter'>
  <img src='/assets/colab-tutorial/gpu.png'>
</div>

You can check your gpu status by type(+code) !nvidia-smi and run it:
<div class='fig figcenter'>
  <img src='/assets/colab-tutorial/check.png'>
</div>

In order to load data, we need to mount our google drive using following command. Note that you need to do this evertime you open a .ipynb with colab.
```
import os
print(os.getcwd())
from google.colab import drive
drive.mount('/content/drive')
 
path = "/content/drive/My Drive/cs682/assignment1"
os.chdir(path)
print(os.getcwd())
```

You will see this:
<div class='fig figcenter'>
  <img src='/assets/colab-tutorial/mount.png'>
</div>

Now your root dir is "/content/drive/My Drive/cs682/assignment1" and you can run the code in the .ipynb. 

Colab comes with most of common package. If you need to install package or update package (for example numpy), simply run 
```
!pip install numpy
```
To check on existing packages:
```
!pip list
```


Terminal command are supported but with slightly change (add !):
```
ls -> !ls
nvidia-smi -> !nvidia-smi
cd dir -> %cd dir (cd need to add % which is special)
```

If you have any question, you can refer this [tutorial](https://colab.research.google.com/notebooks/intro.ipynb#scrollTo=-Rh3-Vt9Nev9).
