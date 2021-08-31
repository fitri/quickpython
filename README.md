# Real Quick Tips How to Implement Certain Python Feature
The list is not in order and continue adding the list based on need.

The code indention format for this post is 4 spaces.

There's no fixed format for the code, it might been working code or might just been a placeholder for example purposes.

The code in this list should only do one thing, one.

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

#add parameter shell=True if wildcard not working
#only Popen stdout process can be pass as stdin
```

### Opening file with generator
```python
def openingfile(patlist):
    with open(patlist, 'r') as listfile:
        for pattern in listfile.readlines():
            yield pattern

#calling the function
for i in openingfile('list.file'):
    print(i)
```

### Getting and update value for dictionary
```python
dict = {}

#adding value
dict['name'] = fitri

#get value
dict.get('name')
```

### Stripping string
```python
text = "   hello   "

#remove left trailing char
text.lstrip()

#remove right trailing char
text.rstrip()

#remove all trailing char
text.strip()

#strip custom char, must be from either end (can be applied in both rstrip and lstrip)
text.strip('o ')
```
### Passing file's arg to script
```python
import argparse

#create parser object
parser = argparse.ArgumentParser()

#add argument based on positional
parser.add_argument('filename')

#parsing back the arg
print(parser.parse_args().filename)
```
### Read and writing csv file
```python
import csv

#reading the csv file
with open('file.csv','r') as csvfile:
    readcsv = csv.reader(csvfile)
    for row in readcsv:
        print(row)
        
#writing csv file
with open('file.csv','w') as csvfile:
    writecsv = csv.writer(csvfile)
    writecsv.writerow(['one', 'two'])
```
### Add value to dict
```python
sample = {
    "data":"existing"
}

#using format dictionary[key] = value
sample["latest"] = "new"
```
### Check if key exist in dictionary
```python
sample = {
    "data":"existing"
}
#using if else and builtin method keys()
if "data" in sample.keys():
    return True
```
### Return default value from dictionary
```python
database = {
    'user':'fitri',
    'id': '707'
}

#return None (or any value) if key not found in database.
database.get('fatin', None)

```
### Passing value to generator
```python
def generatorfunction():
    x = yield x
    print (x)
    
>>> hi = generatorfunction()
>>> hi.__next__()
>>> hi.send('Fitri')
>>> Fitri

#generator need to be started first with __next__ before proceeding sending the datatypes.

```
### Iterating generator inside of generator
```python
def generatorfirst(n):
    for i in range(n):
        yield i 
        
def generatorsecond(n):
    yield 'Start here'
    yield from generatorfirst()
    yiend 'End here'
    
>>> hi = generatorssecond()
>>> hi.__next__()
>>> Start here
>>> Hi.__next()
>>> 0
...x98
>>> End here

#using yield from, the generator can iterate over generator object just like loop
#the key yield from need to be inside of function

```
### Pass output from unix command pipeline into python script
```python
#save this infot file.py
import fileinput

with fileinput.input() as f_input:
    for line in f_input:
        print(line, end='')

>>> ls -l | python file.py

#the pipeline will pass the to the script, process and get the output.
```
        
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
