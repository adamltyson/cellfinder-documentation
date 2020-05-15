---
description: Downloading the files that amap needs for registration
---

# Downloading files

## D**ownload atlas \(optional\)**

When amap runs, the appropriate reference atlas will be downloaded \(if not previously done so\). If you would like to download in advance to save time \(or if you will not have an internet connection\) please use `amap_download`.

Currently, the only supported atlas is the Allen reference mouse brain, originally from [here](http://help.brain-map.org/display/mouseconnectivity/API#API-DownloadAtlas). The atlas will download into `./amap/atlas`.

In the future, other atlases will be available, and you will be able to choose which is downloaded.

If you want to modify the am amap download, use:

* `--atlas-install-path` Supply a path to download the atlas elsewhere. This 

  should also update the default `registration.conf` file so that the correct 

  atlas is sourced. Alternatively, use this command to tell amap where an 

  existing atlas is, to save it being downloaded twice. \(Requires 20GB 

  disk space\)

* `--atlas download path` The path to download the atlas into. 

  \(Requires 1.2GB disk space\). Defaults to `/tmp`.

