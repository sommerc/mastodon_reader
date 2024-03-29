# Mastodon Reader for Python
Import the *spots and links tables*, *features*, *tags* and meta data from a *Mastodon project file*.

ported to Python from: [matlab-mastodon-importer](https://github.com/mastodon-sc/matlab-mastodon-importer)

## Example
Read the mastodon file:

```python
from mastodon_reader import MastodonReader

mr = MastodonReader("demo/demo.mastodon")

# show meta data
meta_data = mr.read_metadata()

# read (networkX) graph representation, spot and link tables with features and tags columns
graph, spots, links, tag_definition = mr.read(tags=True, features=True)

```
or read information separately

```python
# read only spot and link tables
spots, links = mr.read_tables()

# read tag_definition and add tags as new columns to the spot and link tables
tag_definition = mr.read_tags(spots, links)

# read features and add as new columns to the spot and link tables
mr.read_features(spots, links)

# create networkX DiGraph representation form spots and links
graph = mr.create_nx_graph(spots, links)
```

## Installation
#### Current version
`pip install git+git://github.com/mastodon-sc/python-mastodon-importer.git`

#### pip
`pip install Mastodon-Reader`

more information [on PyPi](https://pypi.org/project/Mastodon-Reader/)

#### Dependencies
* numpy
* pandas
* networkx


