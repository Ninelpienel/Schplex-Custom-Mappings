# Just a Custom Mapping file for [PlexAniSync](https://github.com/RickDB/PlexAniSync)

To enable the sync function for specials, change the lines of the following files:

#### [custom_mappings_schema.json, line 46](https://github.com/RickDB/PlexAniSync/blob/master/custom_mappings_schema.json#L46):

```json
"minimum": 1
```

to

```json
"minimum": 0
```

#### [plexanisync/plexmodule.py, line 181](https://github.com/RickDB/PlexAniSync/blob/master/plexanisync/plexmodule.py#L181):

```py
lambda season: season.seasonNumber > 0 and season.viewedLeafCount > 0,
```

to

```py
lambda season: season.seasonNumber >= 0 and season.viewedLeafCount > 0,
```
