# ExpressionWrapper

ExpressionWrapper prend en parametre une expression pour en sortir un output_field. 
Cela nécessite de l'utilisation de l'expression ***F() *** pour faire des déclaration. 
``` python
from django.db.models import DateTimeField, ExpressionWrapper, F

Ticket.objects.annotate(
    expires=ExpressionWrapper(
        F("active_at") + F("duration"), output_field=DateTimeField()
    )
)
```

Ou alors : 

``` python 
car = Company.objects.annotate(built_by=F("manufacturer"))[0]
 car.manufacturer
<Manufacturer: Toyota>
 car.built_by
```
