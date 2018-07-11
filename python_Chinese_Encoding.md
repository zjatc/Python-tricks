1.problem: " UnicodeEncodeError: 'ascii' codec can't encode characters in position 56-57: ordinal not in range(128) " in Python3
  solution: 
  1.1 check sys.stdout.encoding:
  ```
  import sys
  sys.stdout.encoding 
  out >> # 'ANSI_X3.4-1968'
  ```
  this encoding set cannot print out Chinese
  1.2 use PYTHONIOENCODING to solve this problem
  run python script as following format
  ```
  PYTHONIOENCODING=utf-8 python python_script.py
  ```
  ||
  redefine stdout
  ```
  sys.stdout = codecs.getwriter("utf-8")(sys.stdout.detach())
  # print logs
  sys.stdout.write("log message...")
  ```
