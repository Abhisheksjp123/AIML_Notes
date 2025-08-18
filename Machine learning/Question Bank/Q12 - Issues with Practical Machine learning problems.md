Problem 1: Don't remember attributes of various ML methods. Its fine in normal days as intellisense helps. But in case of terminals in tests, intellisense does not work.
Solution: 
a. You can use following methods to get the list of attributes:
for example to get attributes for == pd.read_csv==
1. Get help documentation
    help(pd.read_csv)
2. See the function signature and docstring 
   pd.read_csv?
3. In Jupyter, use shift+tab after typing the function 
   pd.read_csv( # then press Shift+Tab

b. to get the attributes of a dataframe (like astype etc.) you can use:
dir(df) ----> it gives you list of methods supported for the data frame
