json-lua
========

A JSON encoder/decoder for Lua.

Tested on Lua 5.1 (inside of LOVE2D), no guarantees for other versions.

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

License
======

The MIT License (MIT)

Copyright (c) 2014 Ted Dobyns

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
