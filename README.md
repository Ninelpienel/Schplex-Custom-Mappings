# Just a Custom Mapping file for [PlexAniSync](https://github.com/RickDB/PlexAniSync)

## To use this file, do this:

1. Raname [custom_mappings.yaml.example](https://github.com/RickDB/PlexAniSync/blob/master/custom_mappings.yaml.example) to custom_mappings.yaml
   
2. Open the file in a text editor, remove the whole code and paste this:

```
remote-urls:
  - https://github.com/Ninelpienel/Schplex-Custom-Mappings/blob/main/schplex_custom_mappings.yaml
```

3. Save the file.

Done!

## To enable the sync function for specials, change the lines of the following files:

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
