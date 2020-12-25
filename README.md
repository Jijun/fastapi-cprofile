# fastapi-cprofile

A FastAPI Middleware with cProfile to help stats your service performance. cProfile is a built-in python module that can perform profiling. It is the most commonly used profiler currently.

# Features

 -[x] support custom cprofile param

#Installation

```buildoutcfg
$ pip install fastapi-cprofile -U
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

# License

MIT

