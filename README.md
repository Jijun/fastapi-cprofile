# fastapi-cprofile

A FastAPI Middleware with cProfile to help stats your service performance. 
cProfile is a built-in python module that can perform profiling. It is the most commonly used profiler currently.

# Features

- [x] support custom cprofile param

#Installation

```buildoutcfg
$ pip install fastapi-cprofile
```


# Code Sample

```python
from fastapi_cprofile.profiler import CProfileMiddleware

app = FastAPI()
app.add_middleware(CProfileMiddleware)
```
add cprofile options

```python

from fastapi_cprofile.profiler import CProfileMiddleware
app = FastAPI()
app.add_middleware(CProfileMiddleware, enable=True, print_each_request = True, strip_dirs = False, sort_by='cumulative')

```
or dump out file while shutdown your app then you can use gprof2dot [gprof2dot](https://github.com/jrfonseca/gprof2dot) to view it.

```python

from fastapi_cprofile.profiler import CProfileMiddleware
app = FastAPI()
app.add_middleware(CProfileMiddleware, enable=True, server_app = app, filename='/tmp/output.pstats', strip_dirs = False, sort_by='cumulative')

```

# License

MIT

