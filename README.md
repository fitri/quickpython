# Real Quick Tips How to Implement Certain Python Feature
The list is not in order and continue adding the list based on need.
The indention format for this post is 4 spaces.

### One liner conditional 
```python
value_1 if condition else value_2
```
### Run command and capture the output plus add pipeline for another command
```python
1stcommand = ['ls ', '-l']
2ndcommand = ['egrep', 'log']

output = subprocess.Popen(1stcommand, stdout=subprocess.PIPE, env=EBG_ENV)
output = subprocess.run(2ndcommand, stdin=pat_info.stdout, stdout=subprocess.PIPE)

# add parameter shell=True if wildcard not working
# only Popen stdout process can be pass as stdin
```
### Opening file with generator
```python
def openingfile(patlist):
    with open(patlist, 'r') as listfile:
        for pattern in listfile.readlines():
            yield pattern

# calling the function
for i in openingfile('list.file'):
    print(i)
```


  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
