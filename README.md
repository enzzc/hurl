# hurl

Hashed URL Lookup


## Usage

```bash
# Add a key to the database
$ ./add "https://github.com/enzzc/hurl"
0b2fc95ac2f84a60828139d3c12c1d41dc746044

$ ./add "https://github.com/enzzc/hurl/blob/master/README.md"
f9385b187fbd9a09d74f184092807bcfc88af870

# Retrieve a key by its hash (at least 3 chars)
$ ./lookup 0b2fc9
https://github.com/enzzc/hurl

$ ./lookup f9385b18
https://github.com/enzzc/hurl/blob/master/README.md

# List all entries
$ ./list-all
f9385b187fbd9a09d74f184092807bcfc88af870 https://github.com/enzzc/hurl/blob/master/README.md
0b2fc95ac2f84a60828139d3c12c1d41dc746044 https://github.com/enzzc/hurl
```

The tree will look like this:

```console
$ tree db
db
├── 0b
│   └── 2fc95ac2f84a60828139d3c12c1d41dc746044
└── f9
    └── 385b187fbd9a09d74f184092807bcfc88af870

2 directories, 2 files
```

It acts like a simple key-value store. The layout is inspired by the [Git object database](https://git-scm.com/book/en/v2/Git-Internals-Git-Objects).
