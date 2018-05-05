title: ndarray Indexing & Slicing
--- |

  Indexing & slicing is straight-forward for 1-D arrays. For N-D arrays, it gets a little more complicated. Let's look at the illustration of how indexing works for `ndarray` followed by a code sample.

  ![ndarray indexing](assets/img/ndarray-indexing.png)

  Here is some code for you to play with indexing. Try changing the index numbers and see the effect.
---
type: live-code
code: |
  import numpy as np

  three_d_arr = np.array([
    [
      [0, 1, 2],
      [3, 4, 5]
    ],
    [
      [6, 7, 8],
      [9, 10, 11]
    ]
  ])

  print("three_d_arr[0]:", three_d_arr[0])
  print("three_d_arr[0, 0]:", three_d_arr[0, 0])
  print("three_d_arr[0, 0, 0]:", three_d_arr[0, 0, 0])
--- |

  Let's revisit our example of temperature readings to get a better handle of indexing in `ndarray`. Let's first load the data into a variable.

---
type: live-code
code: |
  import numpy as np

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

--- |

  Now, how would you extract all the readings from station 1 across all hours of the day (as illustrated in this image):

  ![](assets/img/three-d-station-1.png)

  Here is the code to do that.

---
type: live-code
code: |
  temp_readings[ :, 0, :] # All, 0th, All

--- |

  What about all readings for sensor 1 across all stations and all hours (as illustrated here)?

  ![](assets/img/three-d-sensor-1.png)

  Here is the code for the same:

---
type: live-code
code: |
  temp_readings[ :, :, 0]

--- |

  Let's do some exercises for practice.

---
type: categorization-question
question: |
  You are given the following array:

  ```python
  three_d_arr = np.array([
    [
      [0, 1, 2],
      [3, 4, 5]
    ],
    [
      [6, 7, 8],
      [9, 10, 11]
    ]
  ])
  ```

  Match the code with the output it would generate.

mappings:
  three_d_arr[1]: "[ [6, 7, 8], [9, 10, 11] ]"
  three_d_arr[0, 1, 2]: 5
  three_d_arr[1, 0]: "[6, 7, 8]"

---
type: categorization-question
question: |
  You are given the following array:

  ```python
  a = np.array([[[26, 92, 73],
        [12,  7, 36],
        [60, 63, 99]],

       [[37,  9, 17],
        [29, 38, 34],
        [83,  7, 49]],

       [[82, 35, 55],
        [21, 84, 23],
        [12, 65, 76]]])
  ```

  Match the code with the output it would generate.

mappings:
  a[2, 2]: "[12, 65, 76]"
  a[2, 0, 1]: 35
  a[1, 0]: "[37, 9, 17]"
  a[0, 2]: "[60, 63, 99]"

---
type: multiple-choice-question
question: |
  Let's go back to our temperatures dataset. If you wanted all the readings for 6AM (as illustrated below), how would you index it?

  ![](assets/img/three-d-6-am.png)
options:
  - text: "`temp_readings[0, :, :]`"
    correct: true
  - text: "`temp_readings[:, 0, :]`"
  - text: "`temp_readings[0, 0, :]`"
