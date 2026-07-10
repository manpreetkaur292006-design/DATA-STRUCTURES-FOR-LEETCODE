# 📘 Python Dictionary Notes

Short GitHub-ready notes on Python dictionaries, based on the W3Schools dictionary tutorial and related dictionary sections.[1]

## 🧾 Topics Covered

- 📌 Dictionary basics.[1]
- 🔑 Access items.[1]
- ✏️ Change items.[1]
- ➕ Add items.[1]
- ❌ Remove items.[1]
- 🔁 Loop dictionaries.[2]
- 📋 Copy dictionaries.[3]
- 🪆 Nested dictionaries.[1]
- 🛠️ Dictionary methods.[3]
- 🧠 Exercises and code challenge.[1][4]

## 📚 Dictionary Basics

| Concept | Notes | Syntax / Example | Output |
|---|---|---|---|
| Dictionary 📦 | Stores data in key:value pairs.[1] | `d = {"brand": "Ford", "model": "Mustang", "year": 1964}` | `{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}` |
| Ordered 📑 | In Python 3.7+, dictionaries keep insertion order.[1] | `{"a": 1, "b": 2}` | Items stay in inserted order. |
| Changeable ✍️ | Values can be changed after creation.[1] | `d["year"] = 2020` | Dictionary updates. |
| No duplicate keys 🚫 | Duplicate keys overwrite older values.[1] | `{"year": 1964, "year": 2020}` | `{'year': 2020}` |
| Length 📏 | `len()` returns total key:value pairs.[1] | `len(d)` | `3` for the sample dictionary. |
| Type 🏷️ | Python type is `dict`.[1] | `type(d)` | `<class 'dict'>` |
| `dict()` constructor 🏗️ | Another way to create a dictionary.[1] | `d = dict(name="John", age=36)` | `{'name': 'John', 'age': 36}` |

## 🔑 Access Items

| Concept | Notes | Syntax / Example | Output |
|---|---|---|---|
| Access by key 🔍 | Use square brackets with the key name.[1] | `d["model"]` | `'Mustang'` |
| `get()` 🪄 | Returns the value for a given key.[3] | `d.get("model")` | `'Mustang'` |
| `keys()` 🗝️ | Returns all keys.[3] | `d.keys()` | `dict_keys(['brand', 'model', 'year'])` |
| `values()` 📥 | Returns all values.[3] | `d.values()` | `dict_values(['Ford', 'Mustang', 1964])` |
| `items()` 🧩 | Returns key:value pairs as tuples.[3] | `d.items()` | `dict_items([('brand', 'Ford'), ('model', 'Mustang'), ('year', 1964)])` |
| `in` keyword ✅ | Checks whether a key exists.[1] | `'model' in d` | `True` |

## ✏️ Change and Add Items

| Concept | Notes | Syntax / Example | Output |
|---|---|---|---|
| Change value 🔄 | Reassign value using the key.[1] | `d["year"] = 2018` | `year` becomes `2018`. |
| `update()` 🛠️ | Updates existing keys or adds new keys.[3] | `d.update({"year": 2020})` | `year` becomes `2020`. |
| Add item ➕ | Add a new key:value pair directly.[1] | `d["color"] = "red"` | New item added. |
| Add with `update()` 📥 | Can also add new items through `update()`.[3] | `d.update({"color": "red"})` | Adds `color: red`. |

## ❌ Remove Items

| Method | Notes | Syntax / Example | Output |
|---|---|---|---|
| `pop()` 🗑️ | Removes item with the specified key.[3] | `d.pop("model")` | Removes `model`. |
| `popitem()` 📤 | Removes the last inserted key-value pair.[3] | `d.popitem()` | Last item removed. |
| `del` ✂️ | Deletes a specific item.[1] | `del d["model"]` | `model` removed. |
| `clear()` 🧹 | Removes all elements from the dictionary.[3] | `d.clear()` | `{}` |
| `del d` 🚮 | Deletes the whole dictionary variable.[1] | `del d` | Dictionary no longer exists. |

## 🔁 Loop Dictionaries

| Loop Type | Syntax / Example | Output / Use |
|---|---|---|
| Loop through keys 🔑 | `for x in d:` | Prints each key one by one.[2] |
| Loop through values 📥 | `for x in d.values():` | Prints each value.[2] |
| Loop through keys explicitly 📌 | `for x in d.keys():` | Prints each key.[2] |
| Loop through items 🧩 | `for x, y in d.items():` | Prints key and value pairs.[2] |

## 📋 Copy Dictionaries

| Method | Notes | Syntax / Example | Output |
|---|---|---|---|
| `copy()` 📄 | Returns a shallow copy of the dictionary.[3] | `new_d = d.copy()` | New copied dictionary. |
| `dict()` 🏗️ | Can also create a copy from another dictionary.[1] | `new_d = dict(d)` | New copied dictionary. |

## 🪆 Nested Dictionaries

A nested dictionary is a dictionary inside another dictionary.[1] It is useful when one record needs sub-records, such as student data, address details, or multiple objects under one variable.[1]

```python
students = {
    "s1": {"name": "Aman", "marks": 90},
    "s2": {"name": "Riya", "marks": 95}
}
```

Access nested values like this:

```python
students["s1"]["name"]
```

Output:

```python
'Aman'
```

## 🛠️ Dictionary Methods

| Method | Purpose |
|---|---|
| `clear()` 🧹 | Removes all elements.[3] |
| `copy()` 📄 | Returns a copy.[3] |
| `fromkeys()` 🗂️ | Creates a dictionary from given keys and one value.[3] |
| `get()` 🔍 | Returns value of the specified key.[3] |
| `items()` 🧩 | Returns key:value pairs.[3] |
| `keys()` 🗝️ | Returns all keys.[3] |
| `pop()` 🗑️ | Removes item by key.[3] |
| `popitem()` 📤 | Removes last inserted pair.[3] |
| `setdefault()` ⚙️ | Returns key value; inserts key with default value if missing.[3] |
| `update()` 🔄 | Updates dictionary with new key:value pairs.[3] |
| `values()` 📥 | Returns all values.[3] |

## ⚡ Quick Revision

- Dictionary = key:value collection.[1]
- Written using curly braces `{}`.[1]
- Ordered in Python 3.7+.[1]
- Changeable after creation.[1]
- Duplicate keys are not allowed.[1]
- Common methods: `get()`, `keys()`, `values()`, `items()`, `update()`, `pop()`, `clear()`.[3]