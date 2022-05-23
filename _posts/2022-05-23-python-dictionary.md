---
layout: single
title:  "[Python] Dictionary"
---

# Dictionary

### 딕셔너리 쌍 추가하기

- python에서 dictionary 데이터에 자료를 추가하고 싶을 경우 다음과 같이 하면 된다.

```python
>>> a = {1: 'a'}
>>> a[2] = 'b'
>>> a
{1: 'a', 2: 'b'}

#################

>>> a['name'] = 'pey'
>>> a
{1: 'a', 2: 'b', 'name': 'pey'}

# get으로 value 얻기
>>> a = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
>>> a.get('name')
'pey'
>>> a.get('phone')
'0119993323'

```

### 딕셔너리 요소 삭제하기

```python
>>> del a[1]
>>> a
{2: 'b', 'name': 'pey', 3: [1, 2, 3]}

```

### Key 리스트 만들기(keys)

```python
>>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
>>> a.keys()
dict_keys(['name', 'phone', 'birth'])

```

> *[파이썬 3.0 이후 버전의 keys 함수, 어떻게 달라졌나?]
파이썬 2.7 버전까지는 a.keys() 함수를 호출할 때 반환 값으로 dict_keys가 아닌 리스트를 돌려준다. 리스트를 돌려주기 위해서는 메모리 낭비가 발생하는데 파이썬 3.0 이후 버전에서는 이러한 메모리 낭비를 줄이기 위해 dict_keys 객체를 돌려준다. 다음에 소개할 dict_values, dict_items 역시 파이썬 3.0 이후 버전에서 추가된 것들이다. 만약 3.0 이후 버전에서 반환 값으로 리스트가 필요한 경우에는 list(a.keys())를 사용하면 된다. dict_keys, dict_values, dict_items 등은 리스트로 변환하지 않더라도 기본적인 반복(iterate) 구문(예: for문)을 실행할 수 있다.*
> 
- dict_keys 객체를 리스트로 변환하려면 다음과 같이 하면 된다.

```python
>>> list(a.keys())
['name', 'phone', 'birth']

```

### Value 리스트 만들기(values)

```python
>>> a.values()
dict_values(['pey', '0119993323', '1118'])

```

### Key, Value 쌍 얻기(items)

```python
>>> a.items()
dict_items([('name', 'pey'), ('phone', '0119993323'), ('birth', '1118')])

```

### dict[] vs get

```bash
>>> a = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
>>> print(a.get('nokey'))
None
>>> print(a['nokey'])
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'nokey'

```

- 딕셔너리 안에 찾으려는 Key 값이 없을 경우 미리 정해 둔 디폴트 값을 대신 가져오게 하고 싶을 때에는 get(x, ‘디폴트 값’)을 사용하면 편리하다.

```python
>>> a.get('foo', 'bar')
'bar'

```

### 해당 Key가 딕셔너리 안에 있는지 조사하기(in)