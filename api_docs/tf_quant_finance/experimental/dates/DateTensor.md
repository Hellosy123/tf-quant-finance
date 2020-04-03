<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf_quant_finance.experimental.dates.DateTensor" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__add__"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__ge__"/>
<meta itemprop="property" content="__getitem__"/>
<meta itemprop="property" content="__gt__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__le__"/>
<meta itemprop="property" content="__lt__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="__sub__"/>
<meta itemprop="property" content="boolean_mask"/>
<meta itemprop="property" content="broadcast_to"/>
<meta itemprop="property" content="concat"/>
<meta itemprop="property" content="day"/>
<meta itemprop="property" content="day_of_week"/>
<meta itemprop="property" content="day_of_year"/>
<meta itemprop="property" content="days_until"/>
<meta itemprop="property" content="expand_dims"/>
<meta itemprop="property" content="identity"/>
<meta itemprop="property" content="month"/>
<meta itemprop="property" content="ordinal"/>
<meta itemprop="property" content="period_length_in_days"/>
<meta itemprop="property" content="reshape"/>
<meta itemprop="property" content="squeeze"/>
<meta itemprop="property" content="stack"/>
<meta itemprop="property" content="transpose"/>
<meta itemprop="property" content="where"/>
<meta itemprop="property" content="year"/>
</div>

# tf_quant_finance.experimental.dates.DateTensor

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>



Represents a tensor of dates.

Inherits From: [`TensorWrapper`](../../../tf_quant_finance/experimental/dates/periods/tensor_wrapper/TensorWrapper.md)

```python
tf_quant_finance.experimental.dates.DateTensor(
    ordinals, years, months, days
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`ordinals`</b>: Tensor of type int32. Each value is number of days since
  1 Jan 0001. 1 Jan 0001 has `ordinal=1`. `years`, `months` and `days`
  must represent the same dates as `ordinals`.
* <b>`years`</b>: Tensor of type int32, of same shape as `ordinals`.
* <b>`months`</b>: Tensor of type int32, of same shape as `ordinals`
* <b>`days`</b>: Tensor of type int32, of same shape as `ordinals`.

#### Attributes:

* <b>`rank`</b>
* <b>`shape`</b>


## Methods

<h3 id="__add__"><code>__add__</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
__add__(
    period_tensor
)
```

Adds a tensor of periods.


#### Args:


* <b>`period_tensor`</b>: a PeriodTensor object broadcastable to the shape of
  "self".


#### Returns:

The new instance of DateTensor.


When adding months or years, the resulting day of the month is decreased
to the largest valid value if necessary. E.g. 31.03.2020 + 1 month =
30.04.2020, 29.02.2020 + 1 year = 28.02.2021.

#### Example
```python
dates = DateTensor([(2020, 2, 25), (2020, 3, 31)])
new_dates = dates + period.month()
# DateTensor([(2020, 3, 25), (2020, 4, 30)])

new_dates = dates + periods.month([1, 2])
# DateTensor([(2020, 3, 25), (2020, 5, 31)])
```

<h3 id="__eq__"><code>__eq__</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
__eq__(
    other
)
```

Compares two DateTensors by "==", returning a Tensor of bools.


<h3 id="__ge__"><code>__ge__</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
__ge__(
    other
)
```

Compares two DateTensors by ">=", returning a Tensor of bools.


<h3 id="__getitem__"><code>__getitem__</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/tensor_wrapper.py">View source</a>

```python
__getitem__(
    key
)
```

Implements indexing.


<h3 id="__gt__"><code>__gt__</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
__gt__(
    other
)
```

Compares two DateTensors by ">", returning a Tensor of bools.


<h3 id="__le__"><code>__le__</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
__le__(
    other
)
```

Compares two DateTensors by "<=", returning a Tensor of bools.


<h3 id="__lt__"><code>__lt__</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
__lt__(
    other
)
```

Compares two DateTensors by "<", returning a Tensor of bools.


<h3 id="__ne__"><code>__ne__</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
__ne__(
    other
)
```

Compares two DateTensors by "!=", returning a Tensor of bools.


<h3 id="__sub__"><code>__sub__</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
__sub__(
    period_tensor
)
```

Subtracts a tensor of periods.


#### Args:


* <b>`period_tensor`</b>: a periods.PeriodTensor object broadcastable to the shape of
  "self".

#### Returns:

The new instance of DateTensor.


When subtracting months or years, the resulting day of the month is
decreased to the largest valid value if necessary. E.g. 31.03.2020 - 1 month
= 29.02.2020, 29.02.2020 - 1 year = 28.02.2019.

<h3 id="boolean_mask"><code>boolean_mask</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/tensor_wrapper.py">View source</a>

```python
boolean_mask(
    mask, axis=None
)
```

See tf.boolean_mask.


<h3 id="broadcast_to"><code>broadcast_to</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/tensor_wrapper.py">View source</a>

```python
broadcast_to(
    shape
)
```

See tf.broadcast_to.


<h3 id="concat"><code>concat</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/tensor_wrapper.py">View source</a>

```python
@classmethod
concat(
    cls, tensor_wrappers, axis
)
```

See tf.concat.


<h3 id="day"><code>day</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
day()
```

Returns an int32 tensor of days since the beginning the month.

The result is one-based, i.e. yields 1 for first day of the month.

#### Example

```python
dates = DateTensor([(2019, 1, 25), (2020, 3, 2)])
dates.day()  # [25, 2]
```

<h3 id="day_of_week"><code>day_of_week</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
day_of_week()
```

Returns an int32 tensor of weekdays.

The result is zero-based according to Python datetime convention, i.e.
Monday is "0".

#### Example
```python
dates = DateTensor([(2019, 1, 25), (2020, 3, 2)])
dates.days_of_week()  # [5, 1]
```

<h3 id="day_of_year"><code>day_of_year</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
day_of_year()
```

Calculates the number of days since the beginning of the year.


#### Returns:

Tensor of int32 type with elements in range [1, 366]. January 1st yields
"1".


#### Example
```python
dt = dates.from_tuples([(2019, 1, 25), (2020, 3, 2)])
dt.day_of_year()  # [25, 62]
```

<h3 id="days_until"><code>days_until</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
days_until(
    target_date_tensor
)
```

Returns an int32 tensor with numbers of days until the target dates.


#### Args:


* <b>`target_date_tensor`</b>: a DateTensor object broadcastable to the shape of
  "self".

#### Example
```python
dates = DateTensor([(2020, 1, 25), (2020, 3, 2)])
target = DateTensor([(2020, 3, 5)])
dates.days_until(target)  # [40, 3]

targets = DateTensor([(2020, 2, 5), (2020, 3, 5)])
dates.days_until(targets)  # [11, 3]
```

<h3 id="expand_dims"><code>expand_dims</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/tensor_wrapper.py">View source</a>

```python
expand_dims(
    axis
)
```

See tf.expand_dims.


<h3 id="identity"><code>identity</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/tensor_wrapper.py">View source</a>

```python
identity()
```

See tf.identity.


<h3 id="month"><code>month</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
month()
```

Returns an int32 tensor of months.

#### Example
```python
dates = DateTensor([(2019, 1, 25), (2020, 3, 2)])
dates.month()  # [1, 3]
```

<h3 id="ordinal"><code>ordinal</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
ordinal()
```

Returns an int32 tensor of ordinals.

Ordinal is the number of days since 1st Jan 0001.

#### Example
```python
dates = DateTensor([(2019, 3, 25), (1, 1, 1)])
dates.ordinal()  # [737143, 1]
```

<h3 id="period_length_in_days"><code>period_length_in_days</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
period_length_in_days(
    period_tensor
)
```

Returns an int32 tensor with numbers of days each period takes.


#### Args:


* <b>`period_tensor`</b>: a periods.PeriodTensor object broadcastable to the shape of
  "self".

#### Example
```python
dates = DateTensor([(2020, 2, 25), (2020, 3, 2)])
dates.period_length_in_days(period.month())  # [29, 31]

periods = periods.months([1, 2])
dates.period_length_in_days(periods)  # [29, 61]
```

<h3 id="reshape"><code>reshape</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/tensor_wrapper.py">View source</a>

```python
reshape(
    shape
)
```

See tf.reshape.


<h3 id="squeeze"><code>squeeze</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/tensor_wrapper.py">View source</a>

```python
squeeze(
    axis=None
)
```

See tf.squeeze.


<h3 id="stack"><code>stack</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/tensor_wrapper.py">View source</a>

```python
@classmethod
stack(
    cls, tensor_wrappers, axis=0
)
```

See tf.stack.


<h3 id="transpose"><code>transpose</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/tensor_wrapper.py">View source</a>

```python
transpose(
    perm=None
)
```

See tf.transpose.


<h3 id="where"><code>where</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/tensor_wrapper.py">View source</a>

```python
@classmethod
where(
    cls, condition, tensor_wrapper_1, tensor_wrapper_2
)
```

See tf.where. Only three-argument version is supported here.


<h3 id="year"><code>year</code></h3>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/experimental/dates/date_tensor.py">View source</a>

```python
year()
```

Returns an int32 tensor of years.

#### Example
```python
dates = DateTensor([(2019, 1, 25), (2020, 3, 2)])
dates.year()  # [2019, 2020]
```


