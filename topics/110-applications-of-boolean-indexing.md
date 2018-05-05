title: Applications of Boolean Indexing
--- |

  Boolean indexing is a very powerful feature of `ndarray`. Let's look at some of the real world problems that can be solved with boolean indexing.

  Let's consider the following (theoretical) dataset of `max temperature` in Bombay city over 30 consecutive days.

---
type: live-code
code: |
  import numpy as np

  max_temp = np.array([31, 28, 30, 33, 30, 27, 32, 25, 25, 34, 27, 34, 34,
    32, 27, 26, 30, 26, 27, 31, 26, 25, 34, 28, 28, 26, 29, 31, 27, 32])

--- |

  Let's say, we want to find out the number of days on which `max temperature` was more than 30 degree Celsius. First, we'll generate a _boolean index_ using comparison operation.

---
type: live-code
code: |
  index = max_temp > 30

  index

--- |
  As you would recall from our previous discussion, you can apply comparison operator to `ndarray` and that would result in another `ndarray` of boolean values. So, `index` is an array of boolean values. Wherever max temperature was greater than `30`, the `index` will have `True` value. Otherwise, it would have `False`.

  Now, we can use this `index` as a filter on `max_temp` array:

---
type: live-code
code: |
  max_temp_gt_30 = max_temp[index]
  max_temp_gt_30

--- |
  Now, we can just look at the shape of this new array to find out the number of times max temperature was greater than 30.

---
type: live-code
code: |
  max_temp_gt_30.shape

--- |
  We can also combine the entire operation in one line:

---
type: live-code
code: |
  max_temp[ max_temp > 30 ].shape

---
type: fill-in-the-blank-question
question: |
  In max temperature dataset that we just worked with, for how many days was the temperature less than 29?
code: |
  # your code goes here.
blanks:
  - label: Number of days
    answer: 15
solution: |
  max_temp[ max_temp < 29 ].shape

---
type: fill-in-the-blank-question
question: |
  For how many days, the temperature was more than the mean temperature? You can use the [`np.mean()`](https://docs.scipy.org/doc/numpy-1.14.0/reference/generated/numpy.mean.html) function to calculate the mean temperature.
code: |
  # your code goes here
blanks:
  - label: Number of days
    answer: 14
solution: |
  mean = np.mean(max_temp)
  max_temp[ max_temp > mean ].shape

---
type: fill-in-the-blank-question
question: |
  You are given the max and min temperatures for the city of Bombay for 30 consecutive days. Find out the number of days on which the difference between max and min temperature was more than 10 degree Celsius.
code: |
  import numpy as np

  max_temp = np.array([31, 28, 30, 33, 30, 27, 32, 25, 25, 34, 27, 34, 34,
    32, 27, 26, 30, 26, 27, 31, 26, 25, 34, 28, 28, 26, 29, 31, 27, 32])

  min_temp = np.array([24, 22, 20, 22, 21, 22, 22, 21, 23, 21, 21, 21, 20,
    22, 20, 24, 22, 22, 21, 23, 20, 23, 24, 23, 21, 24, 20, 21, 21, 20])

  # rest of the code goes here to perform calculation.
blanks:
  - label: Number of days
    answer: 5
solution: |
  diff = max_temp - min_temp
  diff[ diff > 10 ].shape
