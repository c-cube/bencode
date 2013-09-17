bencode
=======
Bencode (.torrent file format) reader/writer in OCaml without any
external dependencies.

See lib/bencode.mli. Usage is straightforward.

## Installation
For a findlib based install
```
make
make install
```

## Example
In the top level:
```
#require "bencode"
Bencode.decode (`File_path "test.torrent")
```

Will return a data structure representing the bencoded form of the following
type:
```
type t = 
  | Integer of int
  | String of string
  | List of t list
  | Dict of (string * t) list
```