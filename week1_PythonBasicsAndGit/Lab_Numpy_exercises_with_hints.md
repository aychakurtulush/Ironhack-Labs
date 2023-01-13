# numpy exercises

***
This is a collection of exercises that have been collected in the numpy mailing list, on stack overflow
and in the numpy documentation. The goal of this collection is to offer a quick reference for both old
and new users but also to provide a set of exercises for those who teach.


If you find an error or think you've a better way to solve some of them, feel
free to open an issue at <https://github.com/rougier/numpy-100>.
File automatically generated. See the documentation to update questions/answers/hints programmatically.
***

#### 1. Import the numpy package under the name `np` (★☆☆)
`hint: import … as`
import numpy as np

#### 2. Create a null vector of size 10 (★☆☆)
`hint: np.zeros`
null_vector = np.zeros(10,)

#### 3. Create a null vector of size 10 but the fifth value which is 1 (★☆☆)
`hint: array[4]`
null_vector = np.zeros(10)
null_vector[4] = 1

#### 4. Create a vector with values ranging from 10 to 49 (★☆☆)
`hint: arange`
my_vector = np.arange(10,49)

#### 5. Create a 3x3 matrix with values ranging from 0 to 8 (★☆☆)
`hint: reshape`
new_vec = np.arange(0, 8).reshape(3,3)

#### 6. Find indices of non-zero elements from [1,2,0,0,4,0] (★☆☆)
`hint: np.nonzero`
vec1 = [1,2,0,0,4,0] 
np.nonzero(vec1)

#### 7. Create a 3x3 identity matrix (★☆☆)
`hint: np.eye`
vec2 = np.eye(3)

#### 8. Create a 3x3x3 array with random values (★☆☆)
`hint: np.random.random`
vec3 = np.random.random((3,3,3))

#### 9. Create a 10x10 array with random values and find the minimum and maximum values (★☆☆)
`hint: min, max`

vec4 = np.random.random((10, 10))

min = np.min(vec4)
max = np.max(vec4)

#### 10. Create a random vector of size 30 and find the mean value (★☆☆)
`hint: mean`

vec5 = np.random.random((30, ))

mean = np.mean(vec5)


#### 11. Create a 5x5 matrix with values 1,2,3,4 just below the diagonal (★☆☆)
`hint: np.diag`

mat1 = np.diag([1, 2, 3, 4, 5])

#### 12. Normalize a 5x5 random matrix (★☆☆)
`hint: (x -mean)/std`

mat2= np.random.random((5,5))
mean = np.mean(mat2, axis=0)
std = np.std(mat2, axis=0)
normalized_mat2 = (mat2 - mean) / std

#### 13. How to find common values between two arrays? (★☆☆)
`hint: np.intersect1d`

array1 = np.array([1, 2, 3, 4, 5])
array2 = np.array([4, 5, 6, 7, 8])

common_val = np.intersect1d(array1, array2)

#### 14. Create a random vector of size 10 and sort it (★★☆)
`hint: sort`
random_vec = np.random.random((10, ))
random_vec.sort()

#### 15. Create random vector of size 10 and replace the maximum value by 0 (★★☆)
`hint: argmax`
vec_new = np.random.random(10)
vec_new[vec_new.argmax()] = 0

#### 16. Subtract the mean of each row of a matrix (★★☆)
`hint: mean(axis=,keepdims=)`

mat_new = np.random.random((5,5))
new_mat = mat_new - mat_new.mean(axis=1, keepdims=True)


#### 17. How to get the n largest values of an array (★★★)
`Z = np.arange(10000)
np.random.shuffle(Z)
n = 5
hint: np.argsort | np.argpartition`

Z = np.arange(10000)
np.random.shuffle(Z)
n = 5
print(Z[np.argsort(Z)[-n:]])

#### 18. Create a random 5*3 matrix and replace items that are larger than 4 by their squares ( Example:  6 --> 36) 
`hint: np.where`

my_array = np.arange(15,)
my_arr = np.where(my_array > 4, my_array**2, my_array)

my_mat = np.reshape(my_arr, (5,3))
