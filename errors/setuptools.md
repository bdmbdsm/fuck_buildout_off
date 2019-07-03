```
  File "/home/dmytriv/Projects/openprocurement.documentservice.buildout/eggs/zc.buildout-2.2.5-py2.7.egg/zc/buildout/easy_install.py", line 1401, in _final_version
    for part in parsed_version:
TypeError: 'Version' object is not iterable
```

Ознака того, що десь `setuptools` застаріли.
Якщо це відбувається на свіжому білдауті, то:

1. Стерти сліди неуспішної побудови: `rm -rf bin eggs`
2. Зайти в `versions.cfg` і поставити `setuptools` версію `38.5.0`
3. Зовнішні `setuptools` (ті, які юзає `buildout` при побудові проекту) також треба проставити в правильну версію через `pip install --upgrade setuptools==38.5.0`
4. Запустити побудову білдауту.
