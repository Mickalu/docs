Order by for ordering

ex :
``` python 
User.objects.all().order_by('username', '-email')
```

Will oder by username and after desc email

We can't use 
``` python
User.objects.all().order_by('username').order_by('-email')
```

It will order only by the last one 
