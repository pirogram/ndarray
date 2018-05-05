title: ndarray Shape

--- |

  Shape of the array gives you an idea of how elements are stacked within an array. Let's first look at an example followed by the illustration.

---
type: live-code
code: |
  import numpy as np

  one_d_arr = np.array([0, 1, 2])
  print("1d array shape:", one_d_arr.shape)

  # 2-d array (array of array)
  two_d_arr = np.array([
      [0, 1, 2],
      [3, 4, 5]
  ])
  print("2d array shape:", two_d_arr.shape)

  # 3-d array (array of array of array)
  three_d_arr = np.array([[
      [0, 1, 2],
      [3, 4, 5]
    ],[
      [6, 7, 8],
      [9, 10, 11]
  ]])
  print("3d array shape:", three_d_arr.shape)

--- |

  Here is an easy way to visualize it. Note that the outermost array's length is first in the `shape` and innermost array's length is last in the `shape`.

  ![ndarray shape](assets/img/ndarray-shape.png)

---
type: multiple-choice-question
question: |
  What's the shape of `ndarray` created by the following code?

  ```python
  np.array([1, 2])
  ```
options:
  - text: "`(2, )`"
    correct: true
  - text: "`(2, 1)`"
  - text: "`(1, 2)`"

---
type: multiple-choice-question
question: |
  What's the shape of `ndarray` created by the following code?

  ```python
  np.array([[1, 2], [3, 4], [5, 6]])
  ```
options:
  - text: "`(3, 2)`"
    correct: true
  - text: "`(2, 3)`"
  - text: "`(3, 2, 1)`"

---
type: multiple-choice-question
question: |
  What's the shape of `ndarray` we dealt with earlier (temperature readings).

  ![](assets/img/three-d-layout.png)
options:
  - text: "`(2, 3, 2)`"
  - text: "`(2, 3, 3)`"
  - text: "`(3, 2, 3)`"
    correct: true
