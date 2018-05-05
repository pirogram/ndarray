title: Broadcasting
--- |

  We just looked at the vectorized operations on `ndarray`. A related concept is that of *broadcasting*. We know what would happen if we performed `array(1, 2, 3) * array(2, 2, 2)`. We would get `array(2, 4, 6)`. Right? However, what would happen if we were to perform `array(1, 2, 3) * 2`? Let's develop the visual intuition followed by the actual code.

  ![](assets/img/broadcasting.png)

---
type: live-code
code: |
  import numpy as np

  a = np.array([1, 2, 3])
  a * 2

--- |

  Let's put broadcasting to some good use and solve some problems.

---
type: coding-question
question: |
  You are given an array of temperature readings in Celsius. Write some code to convert it into Fahrenheit.
code: |
  import numpy as np

  celsius = np.array([35, 40, 45, 30, 25])
  fahrenheit =  # Write code here
tests: |
  assert np.array_equal(fahrenheit, np.array([95, 104, 113, 86, 77]))
solution: |
  import numpy as np

  celsius = np.array([35, 40, 45, 30, 25])
  fahrenheit = celsius*9/5 + 32

---
type: coding-question
question: |
  You are given morning and evening temperature readings for a city over 7 consecutive days. Find out the percentage change in the temperature. For example, if the morning temperature was `10` and the evening temperature `12`, percentage change is `20%`. On the other hand, if the evening temperature was `8`, the percentage change would be `-20%`.
code: |
  import numpy as np

  morning_temp = np.array([31, 33, 33, 32, 32, 34, 32])
  evening_temp = np.array([27, 26, 26, 27, 27, 29, 28])

  percentage_change =   # write your code here
tests: |
  # np.floor() will round off numbers to nearest lower integer. Easy to compare.
  change = np.floor(percentage_change)
  assert np.array_equal(change, np.array([ 12, 21, 21, 15, 15, 14, 12]))
solution: |
  import numpy as np

  morning_temp = np.array([31, 33, 33, 32, 32, 34, 32])
  evening_temp = np.array([27, 26, 26, 27, 27, 29, 28])

  percentage_change =  (morning_temp - evening_temp)*100/morning_temp

---
type: coding-question
question: |
  Write a function that takes an array as an input. This array has the total sale in a region over last few months. The sale is expressed in Euro and the function converts it to USD and returns the converted values. Assume that 1 Euro is 1.2 USD.
code: |
  import numpy as np

  def usd_to_euros(usd):
    # your code goes here

tests: |
  usd = np.array([120, 130, 110, 220])
  euro = np.array([ 144,  156,  132,  264])
  assert np.array_equal(usd_to_euros(usd), euro)
solution: |
  import numpy as np

  def usd_to_euros(usd):
  return 1.2*usd
