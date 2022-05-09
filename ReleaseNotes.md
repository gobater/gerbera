# Gerbera - UPnP AV Mediaserver.

## v1.11.0

### NEW Features
- Database: Clients and statistics are stored database so restart does not empty client list. Client grouping for play statistics.
- Search: Support searching playlists containers
- Search: Respect ContainerID when performing search
- Import: item class filtering and mapping by file properties allows more sophisticated virtual structure
- Transcoding: Support filtering transcoding profiles by resource properties (like codecs) avoids transcoding if client can play files
- DLNA: Detect DNLA profiles by resource attributes to specify more detailled profile for handling in client
- File type support for WavPack improved: More metadata read with special library if compiled in.
- Support Ubuntu 22.04

### FIXES
- Playlist: Fix parser error
- Playlist: Handle end of file properly
- Browsing: Sort containers first
- Search: search result is sort by title now
- Import: Timestamps in future are not stored for containers

### Code Improvements
- ContentHandler to enum
- ResourceContentType to enum
- ResourceAttribute new style enum
- Config: Autoscan list to plain vector
- ContentManager: Single autoscan list
- Update Duktape version to 2.7.0
- Server: Clean up virtualURL handling
- Add WavPack as library
- Further Cleanups

### General
To benefit from changes a rescan of all media files is recommended

## v1.10.0

### NEW Features
- Add all metadata is seachable
- Add support for ASX playlists
- Drop Ubuntu 20.10, add 21.10
- Improve support for Samsung UPnP extension X_GetFeatureList
- Support for multiple entries in metadata
- Taglib: Handle OGG containing Opus, Speex or FLAC
- WebUI: Display status details on home page
- WebUI: Thumbnails for images and grid view for items

### FIXES
- Block negative track numbers
- Improve matroska parsing speed

### Code Improvements
- Update fmt version

## v1.9.2

- Titles of search results can be configured
- Containers in virtual layout can be defined as search result, so, e.g. albums, located in several places are only found once
- Metadata, like artist, appearing multiple times are now stored in that way and can be sent to UPnP clients as separate entries as well or addressed in layout scripts. If you have a custom js import script which updates metadata you have to modify it using the new properties (see doc on scripting)
- DLNA profile can be configured using video and audio codec, allow devices to pick supported streams
- DLNA profile can be set for transcoding