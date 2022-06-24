# Python Code Standards for Decepticon

## General TL;DR

:white_check_mark: Readable code 

:white_check_mark: Use [PEP8](https://www.python.org/dev/peps/pep-0008/)

:white_check_mark: Use [`typing`](https://docs.python.org/3/library/typing.html)

:white_check_mark: Use [`docstring`](https://www.python.org/dev/peps/pep-0257/)

:white_check_mark: Descriptive variable names

:x: Clever code

:x: Concise code

## Principles

1. DRY (Don't Repeat Yourself)
2. YAGNI (You Aren't Going to Need It)
3. Keep it Pythonic

## Specifics

### Documentation

Using `typing`:
```python
def calculate_something(altitude: float, latitude: float) -> float:
```
---
Using `docstring`s:
```python
def __init__(self, order: int = 0, **kwargs: float):
    """
    :param order: The sequential order of this RoutePoint in the Route
    :param kwargs:
        altitude: float
        latitude: float
        longitude: float
        date_time: float
    """
```
---
Descriptive variable names:

:x:  `x` or `y` or `j` or `k` or `l`

:white_check_mark: `x_value` or `latitude` or `dimension_values` etc.

```python
def build_shape_conflicts(compare_shape: Shape, shapes: List[Shape], include_edges: bool):
    dimensions = compare_shape.dimensions
    for shape in shapes:
        dimensional_conflict = 0
        ...
```