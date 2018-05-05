title: Vectorized Operations
--- |

  When we perform a mathematical or comparison operation on `ndarray`, the operation is performed element-wise. What does it mean? Let's say, we have `array(4, 21, 7)` and `array(4, 12, 9)`. I can perform the operation `array(4, 21, 7) - array(4, 12, 9)` and I would get `array(0, 9, -2)`.

  Here is an easy way to develop a visual intuition for this:

  ![](assets/img/vectorized-subtraction.png)

  Key thing is that subtraction is performed _element wise_. Similarly, if I was to do `array(4, 21, 7) > array(4, 12, 9)`, I would get `array(False, True, False)`. Here is the visualization for the same.

  ![](assets/img/vectorized-comparison.png)

  Let's look at how it manifests in the code:

---
type: live-code
code: |
  import numpy as np

  a1 = np.array([4, 21, 7])
  a2 = np.array([4, 12, 9])

  a1 - a2
  a1 > a2

--- |

  Why is it useful in the context of data science? Let's go back to our example of temperature measurement. Let's say, we have two sensors in our weather station that have recorded temperature in degree celsius every hour. We have 6 readings from each. We are interested in knowing the difference between temperature recorded by them. Are they reporting the same temperature or different? How different?

  Here is a visual intuition for the same followed by the code that would accomplish it.

  ![](assets/img/temperature-difference.png)

---
type: live-code
code: |
  import numpy as np

  sensor1 = np.array([31, 33, 32, 31, 33, 33])
  sensor2 = np.array([30, 32, 32, 31, 32, 33])

  diff = sensor1 - sensor2
  diff

--- |

  Get your hands dirty with some code. In the following snippet, we have generated two random arrays. Try different mathematical operators as well as conditional operators on the same.

---
type: live-code
code: |
  import numpy as np

  # Generate 10 random numbers between 0 - 10.
  a1 = np.random.randint(0, 10, 10)
  a2 = np.random.randint(0, 10, 10)

  a1
  a2

---
type: live-code
code: |
  # Write some code that would give you the sum of two arrays.

---
type: live-code
code: |
  # Write some code that would give you the difference of two arrays.

---
type: live-code
code: |
  # Write some code that compares the two arrays (using '>' operator).

--- |
  Vectorized operations work on multi-dimensional arrays in exactly the same way you would expect them to work. Example:

---
type: live-code
code: |
  import numpy as np

  # Generate two arrays of shape (3, 4)
  a1 = np.random.randint(0, 10, 12).reshape(3, 4)
  a2 = np.arange(12).reshape(3, 4)

  a1
  a2
  a1 - a2
  a1 > a2

--- |

  It can take some time before vectorized operations feel natural to you. Especially, if you have been programming for long, you would be too used to running a loop for such use cases. However, the whole point of `ndarray` is to perform efficient mathematical operations on data. Vectorized operations is a foundational step in that direction.

  As a rule of thumb, if you are running a loop on `ndarray`, you are _probably_ doing something wrong.
