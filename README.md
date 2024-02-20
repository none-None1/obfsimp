[![Downloads](https://static.pepy.tech/badge/obfsimp)](https://pepy.tech/project/obfsimp) [![Downloads](https://static.pepy.tech/badge/obfsimp/month)](https://pepy.tech/project/obfsimp) [![Downloads](https://static.pepy.tech/badge/obfsimp/week)](https://pepy.tech/project/obfsimp)

# obfsimp
 Simple Python 3 obfuscator

## Install
Method 1: Clone this repo and run `python setup.py install`

Method 2: Run `pip install obfsimp`

## Command line usage
Simply run `obfsimp`

## Use in Python program
Use like this:
```python
from obfsimp import Obfuscator
ob=Obfuscator(
    exec=True, # tells the obfuscator to wrap in an exec expression
    add_code=True, # Add junk code
    string_obf=True, # Merge all the strings and bytes into one large bytes
    random_strings # Add random strings in the large bytes
)
code='print("Hello, World!")'
obfuscated=ob(code)
print(obfuscated)
```
The one above uses only some methods supported by obfsimp, there are many other methods, too.

## Restrictions
Some Python code may not work correctly after being obfuscated, for example:
```python
a=3
print(eval('a'))
```
If you pass `rename_variables`, it will not work because `a` will be replaced by another name.

## Examples
In the examples folder, you can see some example programs and obfuscated programs.