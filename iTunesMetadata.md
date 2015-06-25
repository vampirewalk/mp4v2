

# Introduction #

Description of currently known iTunes tags.

**Please Note: This document currently only describes the new, unfinished, metadata connivence API. Information about the old API will be back later**

# Tags used by iTunes #

| Element | Tag | Data Type | Comment | mp4v2 Name|
|:--------|:----|:----------|:--------|:----------|
| Name    | ©nam | UTF-8 string |         | name      |
| Artist  | ©ART | UTF-8 string |         | artist    |
| Album Artist | aART | UTF-8 string |         | albumArtist |
| Album   | ©alb | UTF-8 string  |         | album     |
| Grouping | ©grp |  UTF-8 string | like TIT1 in ID3 | grouping  |
| Composer | ©wrt |  UTF-8 string |         | composer  |
| Comment | ©cmt | UTF-8 string |         | comments  |
| Genre, Pre-defined | gnre | enum      | Standard Genres according to ID3, the iTunes tag is one greater the the corresponding ID3 tag | genre     |
| Genre, User defined | ©gen | UTF-8 string |         | genre     |
| Release Date | ©day | UTF-8 string | YYYY-MM-DD format, may be incomplete (e.g. just the year) | releaseDate |
| Track Number | trkn | binary    |         | track (read only) |
| Disc Number | disk | binary    |         | disk (read only) |
| Tempo   | tmpo |16-bit integer | in beats per minute | tempo     |
| Compilation | cpil | 8-bit integer  (boolean) |         | compilation |
| TV Show Name | tvsh | UTF-8 string  |         | tvShow    |
| TV Episode ID | tven | UTF-8 string  |         | tvEpisodeID |
| TV Season | tvsn | 32-bit integer  |         | tvSeason  |
| TV Episode | tves | 32-bit integer  |         | tvEpisode |
| TV Network | tvnn | UTF-8 string  |         | tvNetwork |
| Description | desc | UTF-8 string | Short description | description |
| Long description | ldes | UTF-8 string | Not limited to 255 bytes. | longDescription |
| Lyrics  | ©lyr | UTF-8 string | Not limited to 255 bytes. | lyrics    |
| Sort Name | sonm | UTF-8 string  |         | sortName  |
| Sort Artist | soar | UTF-8 string  |         | sortArtist |
| Sort Album Artist | soaa | UTF-8 string  |         | sortAlbumArtist |
| Sort Album | soal | UTF-8 string  |         | sortAlbum |
| Sort Composer | soco | UTF-8 string  |         | sortComposer |
| Sort Show | sosn | UTF-8 string  |         | sortTVShow |
| Cover Art | covr | JPEG/PNG/BMP | May have multiple data atoms | artwork   |
| Copyright | cprt | UTF-8 string | Only ISO standard tag | copyright |
| Encoding Tool | ©too |  UTF-8 string | Software used for encoding | encodingTool |
| Encoded By  | ©enc | UTF-8 string | Person/company who encoded the file | encodedBy |
| Purchase Date | purd | UTF-8 string  |         | purchaseDate |
| Podcast | pcst | 8-bit integer  (boolean) |         | podcast (read only) |
| Podcast URL | purl |           |         |           |
| Keywords | keyw | UTF-8 string | Used for Podcasts | keywords (read only) |
| Category | catg | UTF-8 string | Used for Podcasts | category (read only) |
| HD Video | hdvd | 8-bit integer  (boolean)  |         | hdVideo   |
| Media Type | stik | 8-bit integer (enum)  |         | mediaType |
| Content Rating | rtng | 8-bit integer | Explicit/Clean label | contentRating |
| Gapless Playback | pgap | 8-bit integer (boolean) |         | gapless   |
| Purchase Account | apID | UTF-8 string  |         | iTunesAccount (read only) |
| Account Type| akID | 8-bit integer | Identifies the iTunes Store account type  | iTunesAccountType (read only) |
|         | cnID | 32-bit integer | iTunes Catalog ID, used for combing SD  and HD encodes in iTunes | cnID      |
| Country Code | sfID | 32-bit integer | Identifies in which iTunes Store a file was bought  | iTunesCountry (read only) |
|         | atID | 32-bit integer | Use?    | atID      |
|         | plID | 64-bit integer | Use?    |           |
|         | geID | 32-bit integer | Use?    | geID      |
|         | ©st3 |  UTF-8 string | Use?    |           |

**A blank field means that this tag is currently not supported by libmp4v2
Only one gerne tag (gnre or ©gen) is permitted at a time.**

The MP4GetMetadataGerne functions will read whichever is there.
The MP4SetMetadataGerne trys to set the grne tag if its a match to an ID3V1 genre, else it sets the ©gen tag.

## Media Type (stik) ##
| Media Type | stik |
|:-----------|:-----|
| Movie (is now 9) | 0    |
| Normal (Music) | 1    |
| Audiobook  | 2    |
| Music Video | 6    |
| Movie      | 9    |
| TV Show    | 10   |
| Booklet    | 11   |
| Ringtone   | 14   |


## Content Rating (rtng) ##
| Rating | rtng |
|:-------|:-----|
| None   | 0    |
| Clean  | 2    |
| Explicit | 4    |


## iTunes Store Account Type (akID) ##
| Account Type | akID |
|:-------------|:-----|
| iTunes       | 0    |
| AOL          | 1    |


## iTunes Store Country Codes (sfID) ##
| Country | ISO 3166-1 alpha-3 Code | sfID |
|:--------|:------------------------|:-----|
| Australia | AUS                     | 143460 |
| Austria | AUT                     | 143445 |
| Belgium | BEL                     | 143446 |
| Canada  | CAN                     | 143455 |
| Denmark | DNK                     | 143458 |
| Finland | FIN                     | 143447 |
| France  | FRA                     | 143442 |
| Germany  | DEU                     | 143443 |
| Greece  | GRC                     | 143448 |
| Ireland | IRL                     | 143449  |
| Italy   | ITA                     | 143450 |
| Japan   | JPN                     | 143462 |
| Luxembourg | LUX                     | 143451 |
| Netherlands | NLD                     | 143452 |
| New Zealand | NZL                     | 143461 |
| Norway  | NOR                     | 143457 |
| Portugal | PRT                     | 143453 |
| Spain   | ESP                     | 143454 |
| Sweden  | SWE                     | 143456 |
| Switzerland | CHE                     | 143459 |
| United Kingdom | GBR                     | 143444 |
| United States | USA                     | 143441 |

# Sources #
  * [AtomicParsley documentation](http://atomicparsley.sourceforge.net/mpeg-4files.html)
  * Apple iTunes Metadata Format Specification