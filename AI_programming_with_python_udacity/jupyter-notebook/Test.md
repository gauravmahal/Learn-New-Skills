# Informative 

# Header 1
## Header 2
### Header 3

[Udacity's home page](https://www.udacity.com)

**aardvark** or __aardvark__
_gelato_ or *gelato*

```
import requests
response = requests.get('https://www.udacity.com')
```
$$
y = \frac{a}{b+c}
$$

[Cheat Sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)




```python
print ("First", "Notebook")
```

    First Notebook



```python
## will tell the average time 
# %timeit command_to_run 

## If you want to time how long it takes for a whole cell to run
# %%timeit

## Working Interactively
%matplotlib
# (% or %%) for line magics and cell magics
%matplotlib inline
# high resolution 
%config InlineBackend.figure_format = 'retina'

```

    Using matplotlib backend: Qt5Agg



```python
# interactive debugger using the magic command 
%pdb
```

    Automatic pdb calling has been turned ON



```python
numbers = 'hello'
sum (numbers)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-12-e7aa1ca6b683> in <module>
          1 numbers = 'hello'
    ----> 2 sum (numbers)
    

    TypeError: unsupported operand type(s) for +: 'int' and 'str'


    > [0;32m<ipython-input-12-e7aa1ca6b683>[0m(2)[0;36m<module>[0;34m()[0m
    [0;32m      1 [0;31m[0mnumbers[0m [0;34m=[0m [0;34m'hello'[0m[0;34m[0m[0;34m[0m[0m
    [0m[0;32m----> 2 [0;31m[0msum[0m [0;34m([0m[0mnumbers[0m[0;34m)[0m[0;34m[0m[0;34m[0m[0m
    [0m


### pdb [documentation](https://docs.python.org/3/library/pdb.html)

q to exit in prompt

### [Interactive Magic](https://ipython.readthedocs.io/en/stable/interactive/magics.html)


```python

```
