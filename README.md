# Just a Custom Mapping file for [PlexAniSync](https://github.com/RickDB/PlexAniSync)

To enable the sync function for specials, change the lines of the following files:

[custom_mappings_schema.json](https://github.com/RickDB/PlexAniSync/blob/master/custom_mappings_schema.json#L46), line 46:

`                  "minimum": 1`

to

`                  "minimum": 0`

[plexanisync/plexmodule.py](https://github.com/RickDB/PlexAniSync/blob/master/plexanisync/plexmodule.py#L181), line 181

`                        lambda season: season.seasonNumber > 0 and season.viewedLeafCount > 0,`

to

`                        lambda season: season.seasonNumber >= 0 and season.viewedLeafCount > 0,`
