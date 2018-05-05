title: Rank of ndarray
--- |

  While working with `NumPy` code, you are likely to run into the concept of `rank`. `Rank` of an array is closely related to the `shape` and it signifies the number of dimensions in that array. For example, if you look at the following array:

  ```python
  a_1d = np.array([0, 1, 2, 3, 4])
  ```

  This array has only one dimension and hence, it's called an array of `rank 1`. Following is an array of `rank 2`:

  ```python
  a_2d = np.array([
    [0, 1, 2],
    [1, 2, 3]
  ])
  ```

  Early on, we had looked at an array of rank 3 (when we discussed temperature readings):

  ```python
  temp_readings = np.array([
    [     # 6AM
      [31, 32, 31], # station 1
      [29, 28, 30]  # station 2
    ], [  # 7AM
      [32, 34, 33], # station 1
      [33, 32, 34]  # station 2
    ], [  # 8AM
      [33, 32, 34], # station 1
      [32, 33, 33]  # station 2
    ]
  ])
  ```

  You can find out the `rank` of an array by looking at the `array.ndim` attribute. `ndim` stands of number of dimensions (and hence the simplification that rank is just the number of dimensions in an array):

---
type: live-code
code: |
  import numpy as np

  a = np.array([
    [0, 1, 2],
    [1, 2, 3]
  ])

  a.ndim

---
type: fill-in-the-blank-question
question: |
  What's the `rank` of these arrays?

  ```python
  a = np.array([0, 1, 2, 3])

  b = np.array([
    [
      [1, 2, 3],
      [4, 5, 6]
    ]
  ])
blanks:
  - label: a
    answer: 1
  - label: b
    answer: 3
