# Dictionnary 

For flate dictionnarys to one with diff keys values do :

Exemple : {'test': 'yes'}, {'element': 'table'} => {'test': 'yes', 'element': 'table'}
```
dict1 = {'test': 'yes'}
dict2 = {'element': 'table'}

final_dict = {**dict1, **dict2}
# {'test': 'yes', 'element': 'table'}
```
