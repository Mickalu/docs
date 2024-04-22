DRF permet de faire des filters de façon simple pour les ulrs.
Le but étant de permettre au front d'avoir une marge de manoeuvre simple 

Pour le view il faut mettre la class et le type de filtre 

``` python
from django_filters import rest_framework as django_filters
from api import filters

class AlertsView(generics.ListAPIView):
    filter_backends = [django_filters.DjangoFilterBackend]
    filterset_class = filters.AlertsFilter
```

Ensuite il nous faut construire notre filtre dans le dossier des filter_backends
Il faut mettre les fields qui vont nous servir pour filtrer et pour order.
Le champs __ordering__ est là pour permettre via l'url de choisir l'order des datas de retour

``` python
import django_filters
from api import models

class AlertesFilter(django_filters.FilterSet):
    created_at = django_filters.DateFilter()
    content = django_filters.CharFilter(lookup_expr="icontains")

    ordering = django_filters.OrderingFilter(
        fields=(("created_at", "created_at"))
    )

    class Meta:
        model = models.Alerte
        fields = ("created_at", "content", "ordering")
```

Il est aussi possible de faire des filtres avec des valeurs plus et moins avec les opérateurs
gt et lt

``` python
from rest_framework import generics
from django_filters import rest_framework as filters
from myapp import Product


class ProductFilter(filters.FilterSet):
    min_price = filters.NumberFilter(field_name="price", lookup_expr='gte')
    max_price = filters.NumberFilter(field_name="price", lookup_expr='lte')

    class Meta:
        model = Product
        fields = ['category', 'in_stock']


class ProductList(generics.ListAPIView):
    queryset = Product.objects.all()
    serializer_class = ProductSerializer
    filter_backends = (filters.DjangoFilterBackend,)
    filterset_class = ProductFilter
```

Il arrive que nous ayons besoin de changer de filterSet en fonction de la requête du view.
Pour cela on est obliger de changer le filterSet dans le view via la fonction filter_queryset

``` python
class PlanningView(generics.ListAPIView):
    permission_classes=[permissions.IsAuthenticated, api_permissions.PlanningPermissions]
    filter_backends = [rest_filters.DjangoFilterBackend]

    def get_filterset(self, request, queryset):
        filterset_class = self.get_filterset_class()
        return filterset_class(request.query_params, queryset=queryset, request=request)

    def filter_queryset(self, queryset):
        filterset = self.get_filterset(self.request, queryset)
        if filterset is None:
            return queryset
        return filterset.qs

    def get_filterset_class(self):
        user = self.request.user

        if user.groups.filter(name=auth_models.Groupe1).exists():
            return filters.ImmersionFormFilter

        return filters.SlotFilter
```
