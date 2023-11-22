# Django compressor 

When you want to put your code in production, you need to compress all your static files.
Indeed you want each files take minimum place. Your server will thank you. You will earn performance.

So first you need to install Django compressor
```
pip install django-compressor
pip install cssmin && pip install jsmin
```

After you need to write these app into INTALLED_APS :

```
INSTALLED_APPS = (
        # other apps
        "compressor",
)
```
And
```
STATICFILES_FINDERS = (
        # other finders..
        'compressor.finders.CompressorFinder',
)
```

Into settings.py, you can add :
```
COMPRESS_ENABLED = True
COMPRESS_CSS_FILTERS = ["compressor.filters.cssmin.CSSMinFilter"]
COMPRESS_JS_FILTERS = ["compressor.filters.jsmin.JSMinFilter"]

if not COMPRESS_ENABLED:
       COMPRESS_ENABLED = True
       COMPRESS_CSS_FILTERS = ["compressor.filters.cssmin.CSSMinFilter"]
       COMPRESS_JS_FILTERS = ["compressor.filters.jsmin.JSMinFilter"]
```
