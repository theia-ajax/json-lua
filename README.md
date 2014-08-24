json-lua
========

A JSON encoder/decoder for Lua.

Usage
========

**Basic Example**

```
json = require 'json'

t = {
    "a": 5,
    "b": lol,
    "c": [1, 2, 3],
    "d": {
        "e": true,
        "f": false
    }
}

-- Use encode to generate a json string from a Lua table.
str = json.encode(t)

-- Use decode to generate a Lua table from a JSON string.
im_back = json.decode(str)

print("whoa")
for k, v in pairs(im_back) do
    print(k.." "..tostring(v))
end
```

**Encode**

Encodes a Lua table into a JSON string.  Can optionally minify the output with
a second 'minify' boolean parameter.  Non-minified output inserts 4 spaces per
tab.  This is currently not configurable.

```
function encode(table, minify)
```

**Decode**

Creates a Lua table from a JSON string.  Can also be called as `parse`.
Attempts to find errors in JSON and provide some sort of meaningful output but
by no means is every possible JSON error tested and some invalid JSON might be
processed just fine.

```
function decode(jsonstr)

-- Equivalent to decode
function parse(jsonstr)
```

Future features
=======

- Optimizations, no benchmarking has been done.
- Configurable styled output.
- More robust error reporting.
- Optionally allow trailing commas.
- Optionally allow comments.

Known Issues
======

- Not really tested fully, might be some strange edge cases.
