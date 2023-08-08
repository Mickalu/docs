# Improve performance

## select_related

[Official doc](https://docs.djangoproject.com/en/4.1/ref/models/querysets/#select-related)
Usually for getting an object value we use : 
```
# Hits the database.
e = Entry.objects.get(id=5)

# Hits the database again to get the related Blog object.
b = e.blog
```

The problem is we hit database twice. In term of performance, it's not perfect. Instead we can use : 
```
# Hits the database.
e = Entry.objects.select_related('blog').get(id=5)

# Doesn't hit the database, because e.blog has been prepopulated
# in the previous query.
b = e.blog
```

With select_related we hit database only once and we get better performance. 

We can use it for any queryset of object 
Example :
```
from django.utils import timezone

# Find all the blogs with entries scheduled to be published in the future.
blogs = set()

for e in Entry.objects.filter(pub_date__gt=timezone.now()).select_related('blog'):
    # Without select_related(), this would make a database query for each
    # loop iteration in order to fetch the related blog for each entry.
    blogs.add(e.blog)
```

Other example :
```
Entry.objects.filter(pub_date__gt=timezone.now()).select_related('blog')
Entry.objects.select_related('blog').filter(pub_date__gt=timezone.now())
```
