# Dictionnary 

For flate dictionnarys to one with diff keys values do :

Exemple : {'test': 'yes'}, {'element': 'table'} => {'test': 'yes', 'element': 'table'}
```
dict1 = {'test': 'yes'}
dict2 = {'element': 'table'}

final_dict = {**dict1, **dict2}
# {'test': 'yes', 'element': 'table'}
```

If you want to test if one of your list element has specificity do this :

``` python
list_a = [1,2,3,4,5]
any(x == 2 for x in list_a)
```

You can do this for checking if an elem is in another list : 

``` python
list_a = [1,2,3]
list_b = [3,4,5]

any(x in list_b for x in list_a)
# True
```

On the other hand if you want to check all elem in list you can do :

``` python
list_a = [1,2,3]
list_b = [3,4,5]

all(x in list_b for x in list_a)
# False
```

