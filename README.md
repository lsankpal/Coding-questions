# Coding-questions

Given a string s and an array of positive integers sizes, where the sum of all the elements of sizes is equal to the length of s.

Split the given s into substrings of lengths sizes[0], sizes[1], sizes[2], ..
Swap the obtained substrings in pairs. Swap the 1st one with 2nd, 3rd one with 4th, ..
Concatenate the swapped substrings back to one string and return the resulting string as the answer

.
.
.
.



def Swap_substrings(s,sizes):
  
  sub_str = []
  concat = []

  s1 = [x for x in s]

  for i in sizes:
      sub_str.append(s1[0:i])
      for j in range(i):
          if s1:
              s1.pop(0)

  for i in range(0,len(sub_str),2):
      if i+1 < len(sub_str):
          concat.extend(sub_str[i+1])
          concat.extend(sub_str[i])
      else:
          concat.extend(sub_str[i])

  output = "".join(concat)

  return(output)
