# Generics Views

Generics views permit to create all default views like update, create, delete, get. 
For using that you need to use serializer and models. You can use permissions and filters with it.

## For Create :

```
class CreateObject(generics.CreateAPIView):
    serializer_class = ObjectSerializer
```

You need to create Serializer before but now you just need to call url to create your object.

## For Update specific object :
```
class GetObjectAPI(generics.UpdateAPIView):
    serializer_class = ObjectSerializerSerializer
    queryset = Object.objects.all()
    lookup_field = 'pk'
```

lookup_field : it's variable you need to look for getting the object. 
Here the url looks like :
```
/object/update/<int:pk>/
```

## For delete 

```
class GetObjectAPI(generics.DestroyAPIView):
    serializer_class = ObjectSerializerSerializer
    queryset = Object.objects.all()
    lookup_field = 'pk'
```

Same than Update

## For getting list 

```
class GetListObjectAPI(generics.ListAPIView):
    serializer_class = ObjectSerializer
    queryset = UPR.objects.all()
```

The url returns serializer(data=queryset).data

## For getting object

```
class GetListObjectAPI(generics.RetrieveAPIView):
    serializer_class = ObjectSerializer
    queryset = UPR.objects.all()
```

The url returns serializer(data=queryset).data
