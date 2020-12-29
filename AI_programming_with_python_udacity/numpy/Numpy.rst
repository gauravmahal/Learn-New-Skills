.. code:: ipython3

    import numpy as np

.. code:: ipython3

    # We create a 1D ndarray that contains only integers
    x = np.array([1, 2, 3, 4, 5])
    
    # We print x
    print()
    print('x = ', x)
    print()
    
    # We print information about x
    print('x has dimensions:', x.shape)
    print('x is an object of type:', type(x))
    print('The elements in x are of type:', x.dtype)


.. parsed-literal::

    
    x =  [1 2 3 4 5]
    
    x has dimensions: (5,)
    x is an object of type: <class 'numpy.ndarray'>
    The elements in x are of type: int64


.. code:: ipython3

    # We create a rank 2 ndarray that only contains integers
    Y = np.array([[1,2,3],[4,5,6],[7,8,9], [10,11,12]])
    print('Y = \n', Y)
    
    # We print information about Y
    print('Y has dimensions:', Y.shape)
    print('Y has a total of', Y.size, 'elements')
    print('Y is an object of type:', type(Y))
    print('The elements in Y are of type:', Y.dtype)


.. parsed-literal::

    Y = 
     [[ 1  2  3]
     [ 4  5  6]
     [ 7  8  9]
     [10 11 12]]
    Y has dimensions: (4, 3)
    Y has a total of 12 elements
    Y is an object of type: <class 'numpy.ndarray'>
    The elements in Y are of type: int64


.. code:: ipython3

    # We create a rank 1 ndarray of floats but set the dtype to int64
    x = np.array([1.5, 2.2, 3.7, 4.0, 5.9], dtype = np.int64)
    print('x = ', x)
    
    # We print the dtype x
    print('The elements in x are of type:', x.dtype)


.. parsed-literal::

    x =  [1 2 3 4 5]
    The elements in x are of type: int64


.. code:: ipython3

    # We create a rank 1 ndarray
    x = np.array([1, 2, 3, 4, 5])
    
    # We save x into the current directory as 
    np.save('my_array', x)

.. code:: ipython3

    # We load the saved array from our current directory into variable y
    y = np.load('my_array.npy')
    print('y = ', y)
    
    # We print information about the ndarray we loaded
    print('y is an object of type:', type(y))
    print('The elements in y are of type:', y.dtype)


.. parsed-literal::

    y =  [1 2 3 4 5]
    y is an object of type: <class 'numpy.ndarray'>
    The elements in y are of type: int64


Using Built-in Functions to Create ndarrays
-------------------------------------------

.. code:: ipython3

    # We create a 3 x 4 ndarray full of zeros. 
    X = np.zeros((3,4))
    # X = np.ones((3,2))
    # np.full(shape, constant value)
    print('X = \n', X)
    
    # We print information about X
    print('X has dimensions:', X.shape)
    print('X is an object of type:', type(X))
    print('The elements in X are of type:', X.dtype)


.. parsed-literal::

    X = 
     [[0. 0. 0. 0.]
     [0. 0. 0. 0.]
     [0. 0. 0. 0.]]
    X has dimensions: (3, 4)
    X is an object of type: <class 'numpy.ndarray'>
    The elements in X are of type: float64


.. code:: ipython3

    # We create a 5 x 5 Identity matrix. 
    X = np.eye(5)
    
    print('X = \n', X)
    
    # Create a 4 x 4 diagonal matrix that contains the numbers 10,20,30, and 50
    # on its main diagonal
    X = np.diag([10,20,30,50])
    print('X = \n', X)


.. parsed-literal::

    X = 
     [[1. 0. 0. 0. 0.]
     [0. 1. 0. 0. 0.]
     [0. 0. 1. 0. 0.]
     [0. 0. 0. 1. 0.]
     [0. 0. 0. 0. 1.]]
    X = 
     [[10  0  0  0]
     [ 0 20  0  0]
     [ 0  0 30  0]
     [ 0  0  0 50]]


.. code:: ipython3

    # We create a rank 1 ndarray that has sequential integers from 0 to 9
    x = np.arange(10)
    print('x = ', x)
    
    # We create a rank 1 ndarray that has evenly spaced integers from 1 to 13 in steps of 3.
    x = np.arange(1,14,3)
    print('x = ', x)


.. parsed-literal::

    x =  [0 1 2 3 4 5 6 7 8 9]
    x =  [ 1  4  7 10 13]


.. code:: ipython3

    # We create a rank 1 ndarray that has 10 integers evenly spaced between 0 and 25,
    # with 25 excluded.
    x = np.linspace(0,25,10, endpoint = False)
    print('x = ', x)
    
    # We create a rank 1 ndarray with 10 integers evenly spaced between 0 and 50,
    # with 50 excluded. We then reshape it to a 5 x 2 ndarray
    X = np.linspace(0,50,10, endpoint=False).reshape(5,2)
    print('X = \n', X)


.. parsed-literal::

    x =  [ 0.   2.5  5.   7.5 10.  12.5 15.  17.5 20.  22.5]
    X = 
     [[ 0.  5.]
     [10. 15.]
     [20. 25.]
     [30. 35.]
     [40. 45.]]


.. code:: ipython3

    # We create a 3 x 2 ndarray with random integers in the half-open interval [4, 15).
    X = np.random.randint(4,15,size=(3,2))
    
    print('X = \n', X)


.. parsed-literal::

    X = 
     [[11 10]
     [ 7  9]
     [ 5 10]]


.. code:: ipython3

    # We create a 1000 x 1000 ndarray of random floats drawn from normal (Gaussian) distribution
    # with a mean of zero and a standard deviation of 0.1.
    X = np.random.normal(0, 0.1, size=(1000,1000))
    
    # We print X
    print()
    print('X = \n', X)
    print()
    
    # We print information about X
    print('X has dimensions:', X.shape)
    print('X is an object of type:', type(X))
    print('The elements in X are of type:', X.dtype)
    print('The elements in X have a mean of:', X.mean())
    print('The maximum value in X is:', X.max())
    print('The minimum value in X is:', X.min())
    print('X has', (X < 0).sum(), 'negative numbers')
    print('X has', (X > 0).sum(), 'positive numbers')


.. parsed-literal::

    
    X = 
     [[ 0.04054401  0.04334012  0.09534865 ... -0.01175753 -0.18863794
      -0.07340416]
     [-0.04343477  0.09266155  0.04125173 ... -0.00201531 -0.15910786
      -0.27990323]
     [-0.02479624 -0.03944212 -0.08055817 ...  0.12207836  0.14397383
      -0.02409611]
     ...
     [-0.119301   -0.12017142  0.2195497  ...  0.15320017  0.1819088
      -0.10485609]
     [-0.11922948 -0.02389552  0.12814463 ... -0.09069671 -0.0535639
       0.13348655]
     [ 0.05309184 -0.05188042  0.07460623 ... -0.00062053 -0.29612591
      -0.00436376]]
    
    X has dimensions: (1000, 1000)
    X is an object of type: <class 'numpy.ndarray'>
    The elements in X are of type: float64
    The elements in X have a mean of: -7.630158764457897e-05
    The maximum value in X is: 0.4849427008794246
    The minimum value in X is: -0.48221540297246346
    X has 500359 negative numbers
    X has 499641 positive numbers


Accessing, Deleting, and Inserting Elements Into ndarrays
---------------------------------------------------------

.. code:: ipython3

    # We create a rank 2 ndarray
    Y = np.array([[1,2,3],[4,5,6],[7,8,9]])
    print('Original Y = \n', Y)
    
    # We delete the first row of y
    w = np.delete(Y, 0, axis=0)
    print('w = \n', w)
    
    # We delete the first and last column of y
    v = np.delete(Y, [0,2], axis=1)
    print('v = \n', v)
    
    # We append a new row containing 7,8,9 to y
    v = np.append(Y, [[7,8,9]], axis=0)
    print('w = \n', v)
    
    # We append a new column containing 9 and 10 to y
    q = np.append(Y,[[9],[10],[11]], axis=1)
    print('w = \n', q)


.. parsed-literal::

    Original Y = 
     [[1 2 3]
     [4 5 6]
     [7 8 9]]
    w = 
     [[4 5 6]
     [7 8 9]]
    v = 
     [[2]
     [5]
     [8]]
    w = 
     [[1 2 3]
     [4 5 6]
     [7 8 9]
     [7 8 9]]
    w = 
     [[ 1  2  3  9]
     [ 4  5  6 10]
     [ 7  8  9 11]]


.. code:: ipython3

    # We create a rank 1 ndarray 
    x = np.array([1,2])
    print('x = ', x)
    
    # We create a rank 2 ndarray 
    Y = np.array([[3,4],[5,6]])
    print('Y = \n', Y)
    
    # We stack x on top of Y
    z = np.vstack((x,Y))
    print('z = \n', z)
    
    # We stack x on the right of Y. We need to reshape x in order to stack it on the right of Y. 
    w = np.hstack((Y,x.reshape(2,1)))
    print('w = \n', w)


.. parsed-literal::

    x =  [1 2]
    Y = 
     [[3 4]
     [5 6]]
    z = 
     [[1 2]
     [3 4]
     [5 6]]
    w = 
     [[3 4 1]
     [5 6 2]]


Slicing ndarrays
----------------

1. ndarray[start:end]
2. ndarray[start:]
3. ndarray[:end]

.. code:: ipython3

    # We create a 4 x 5 ndarray that contains integers from 0 to 19
    X = np.arange(20).reshape(4, 5)
    print('X = \n', X)
    
    # We select all the elements that are in the 2nd through 4th rows and in the 3rd to 5th columns
    Z = X[1:,2:5]
    print('Z = \n', Z)


.. parsed-literal::

    X = 
     [[ 0  1  2  3  4]
     [ 5  6  7  8  9]
     [10 11 12 13 14]
     [15 16 17 18 19]]
    Z = 
     [[ 7  8  9]
     [12 13 14]
     [17 18 19]]


.. code:: ipython3

    # create a copy of the slice using the np.copy() function
    Z = np.copy(X[1:4,2:5])
    
    #  create a copy of the slice using the copy as a method
    W = X[1:4,2:5].copy()
    
    # We change the last element in Z to 555
    Z[2,2] = 555
    
    # We change the last element in W to 444
    W[2,2] = 444
    
    print('X = \n', X)
    print('Z = \n', Z)
    print('W = \n', W)


.. parsed-literal::

    X = 
     [[ 0  1  2  3  4]
     [ 5  6  7  8  9]
     [10 11 12 13 14]
     [15 16 17 18 19]]
    Z = 
     [[  7   8   9]
     [ 12  13  14]
     [ 17  18 555]]
    W = 
     [[  7   8   9]
     [ 12  13  14]
     [ 17  18 444]]


.. code:: ipython3

    print('X = \n', X)
    # We print the elements above the main diagonal of X
    print('y =', np.diag(X, k=1))
    print()
    
    # Create 3 x 3 ndarray with repeated values
    X = np.array([[1,2,3],[5,2,8],[1,2,3]])
    print('X = \n', X)
    
    # We print the unique elements of X 
    print('The unique elements in X are:',np.unique(X))


.. parsed-literal::

    X = 
     [[ 0  1  2  3  4]
     [ 5  6  7  8  9]
     [10 11 12 13 14]
     [15 16 17 18 19]]
    y = [ 1  7 13 19]
    
    X = 
     [[1 2 3]
     [5 2 8]
     [1 2 3]]
    The unique elements in X are: [1 2 3 5 8]


Boolean Indexing, Set Operations, and Sorting
---------------------------------------------

.. code:: ipython3

    # We create a 5 x 5 ndarray that contains integers from 0 to 24
    X = np.arange(25).reshape(5, 5)
    print('Original X = \n', X)
    # We use Boolean indexing to select elements in X:
    print('The elements in X that are greater than 10:', X[X > 10])
    
    # We use Boolean indexing to assign the elements that are between 10 and 17 the value of -1
    X[(X > 10) & (X < 17)] = -1
    print('X = \n', X)


.. parsed-literal::

    Original X = 
     [[ 0  1  2  3  4]
     [ 5  6  7  8  9]
     [10 11 12 13 14]
     [15 16 17 18 19]
     [20 21 22 23 24]]
    The elements in X that are greater than 10: [11 12 13 14 15 16 17 18 19 20 21 22 23 24]
    X = 
     [[ 0  1  2  3  4]
     [ 5  6  7  8  9]
     [10 -1 -1 -1 -1]
     [-1 -1 17 18 19]
     [20 21 22 23 24]]


.. code:: ipython3

    # We create a rank 1 ndarray
    x = np.array([1,2,3,4,5])
    
    # We create a rank 1 ndarray
    y = np.array([6,7,2,8,4])
    
    # We use set operations to compare x and y:
    print()
    print('The elements that are both in x and y:', np.intersect1d(x,y))
    print('The elements that are in x that are not in y:', np.setdiff1d(x,y))
    print('All the elements of x and y:',np.union1d(x,y))


.. parsed-literal::

    
    The elements that are both in x and y: [2 4]
    The elements that are in x that are not in y: [1 3 5]
    All the elements of x and y: [1 2 3 4 5 6 7 8]


.. code:: ipython3

    # We create an unsorted rank 1 ndarray
    x = np.random.randint(1,11,size=(10,))
    print('Original x = ', x)
    print('Sorted x (out of place):', np.sort(x))
    # When we sort out of place the original array remains intact. To see this we print x again
    print('x after function sorting:', x)
    
    # We sort x and print the sorted array using sort as a method.
    x.sort()
    print('x after method sorting:', x)


.. parsed-literal::

    Original x =  [8 9 5 9 1 1 7 2 1 7]
    Sorted x (out of place): [1 1 1 2 5 7 7 8 9 9]
    x after function sorting: [8 9 5 9 1 1 7 2 1 7]
    x after method sorting: [1 1 1 2 5 7 7 8 9 9]


.. code:: ipython3

    # We create an unsorted rank 2 ndarray
    X = np.random.randint(1,11,size=(5,5))
    print('Original X = \n', X)
    
    # We sort the columns of X and print the sorted array
    print('X with sorted columns :\n', np.sort(X, axis = 0))


.. parsed-literal::

    Original X = 
     [[ 1 10 10  5  9]
     [ 2 10 10  4  2]
     [ 2  4  1  3  4]
     [ 5 10  5  3  3]
     [ 4  3 10  9  4]]
    X with sorted columns :
     [[ 1  3  1  3  2]
     [ 2  4  5  3  3]
     [ 2 10 10  4  4]
     [ 4 10 10  5  4]
     [ 5 10 10  9  9]]


Arithmetic operations and Broadcasting
--------------------------------------

.. code:: ipython3

    # We create two rank 1 ndarrays
    x = np.array([1,2,3,4])
    y = np.array([5.5,6.5,7.5,8.5])
    print('x = ', x)
    print('y = ', y)
    
    print('multiply(x,y) = ', np.multiply(x,y))
    print('POW(x,2) =',np.power(x,2)) # We raise all elements to the power of 2



.. parsed-literal::

    x =  [1 2 3 4]
    y =  [5.5 6.5 7.5 8.5]
    multiply(x,y) =  [ 5.5 13.  22.5 34. ]
    POW(x,2) = [ 1  4  9 16]


.. code:: ipython3

    # We create a 2 x 2 ndarray
    X = np.array([[1,2,5], [3,4,6]])
    
    print('X = \n', X)
    print('Standard Deviation of all elements in the columns of X:', X.std(axis=0))
    print('Minimum value of all elements in the rows of X:', X.min(axis=1))
    
    # We create a rank 1 ndarray
    x = np.array([1,2,3])
    # We create a 3 x 3 ndarray
    Y = np.array([[1,2,3],[4,5,6],[7,8,9]])
    print('x + Y = \n', x + Y)


.. parsed-literal::

    X = 
     [[1 2 5]
     [3 4 6]]
    Standard Deviation of all elements in the columns of X: [1.  1.  0.5]
    Minimum value of all elements in the rows of X: [1 3]
    x + Y = 
     [[ 2  4  6]
     [ 5  7  9]
     [ 8 10 12]]


When operating on two arrays, NumPy compares their shapes element-wise.
It starts with the trailing dimensions and works its way forward. Two
dimensions are compatible when

-  they are equal, or
-  one of them is 1
