# Real Quick Tips How to Implement Certain Python Feature
The list is not in order and continue adding the list based on need.

### one liner conditional 
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
