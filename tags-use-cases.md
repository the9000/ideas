# Reverse-generalized tags

Add generalizing categories _after_ the value, reversing the
traditional "general to specific" tree structure.

*Examples:* `2012/year`, `2012/july/10/date`, `"Hey Jude"/title`, `10/track`, 
  `"Joe Random"/contact`, `inbox/email`.

* Search for `foo` by default finds any `foo/bar/...`, so generalizations do not hurt.
* Search for `foo/*` explicitly looks for subtags, `foo/` is reverse.
* Search for `*/date` finds all dates -> easy cross-service tagging.

Simple one-level tags can be grouped later, and/or automatically.
Typing for search starts from the most relevant part.

Top-level namespace is polluted with all posible specific tags (anti-tree).

## Limited structure support

`bar/foo` and `baz/foo` can be seen as parts of the same `foo`.
Automatic tag extaction for an audio track:

* title: "Sad but true" -> `"Sad but true"/title`
* artist: "Metallica" -> `Metallica/artist`
* tracknumber: 2 -> `2/tracknumber`
* album: "Black" -> `Black/album`

Automatically tagged as `music/audio/media`, as opposed to e.g. `music/sheet` or
`music/video/media`.

# Tag-based addressing

Non-hierarchical, search-based naming (filesystem):

`{"Sad but true", Metallica}` can be enough.
`{"Sad but true", music/audio, mp3, 192/bitrate}` is more precise.

## Pseudo-hierarchical FS view 

Shows all available tags for the set selected by current path. If the number of
next level-tags is significantly smaller than of top-level tags, the second
level is displayed first:

`foo/a` `bar/a` `foo/b` `baz/b` -> `*/a` `*/b`

Downsides: unstability of levels.

### Version control

Items under a VCS can have tags like `12345/version` or `release/version/tag`,
set by the VCS.

Consider also smth like `987293874932/version/hash`, as in git.

VCS attributes could also live in or be projected to the tag space:
`added/version/control`, etc. This _breaks_ for removed tracked files, though:
no entity to attach `removed/version/control` to.

---

    // other possibilities, seemingly inferior

# Simple 1-level tags (as in twitter)

* *A photo:* #brooklyn #summer2012
* *An email:* #inbox #important #money

# Simple multi-level tags (as in gmail)

* *A photo:* location/brooklyn y2012/summer
* *An email:* inbox money/shopping

# Sublevels as values for superlevel keys

* *A photo:* `location/brooklyn`, `date/"summer 2012"`
* *An email:* `email/inbox`, `money` -- ???
* *A media file:* `artist/Nirvana` `year/1993` -- strange 'year' parent tag

## How to mix key-value properties *and* just tags?

Case in point: a media file.
Properties: `artist="..."`, `year="..."`, `genre="..."`, etc.
Tags: `#starred` `#favorite` `#instrumental`, etc

Case in point: a photo.
Properties: location="...", shutter_speed="...", etc (see exif).
*Structured* properties: date="2012/07/11", rendering / parsing *depends on locale*.

