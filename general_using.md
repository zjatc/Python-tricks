* unnest list in python
```python
nested = [[1,2,3],[6,5,4],[9,10]]

# very slow
flat = sum(nested, [])

# fast
import itertools
flat = list(itertools.chain.from_iterable(nested))
```

* Pandas Related
```python
# collect all items in list-type column
df[COL].apply(pd.Series).stack().drop_duplicates().tolist()

# groupby to DataFrame
df.groupby(COL).count().label.to_frame(name='label_count').reset_index()
df.groupby(COL).apply(lambda x: func(x)).to_frame(name=NEW-COL).reset_index()
```
