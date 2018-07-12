# json

a tiny utility for working with json from stdin

## installation

requires node 8+.

```sh
$ npm i -g @slicey/json
```

## usage

output is prettified for complex structures, and is not shortened. it is also
colored if stdout is a tty :)

```sh
# access from stdin:

$ curl -s https://httpbin.org/headers | json headers.User-Agent
'curl/7.54.0'

$ cat file.json | json mystery.fortune
'👀'

# arrays work:

$ echo '[1, 2, 3]' | json 0
1

# and so do objects:

$ echo '{ "hello there": "warm goodness" }' | json 'hello there'
'warm goodness'

# get you a shibe:

$ curl -s shibe.online/api/shibes | json 0 | xargs open # macOS
$ curl -s shibe.online/api/shibes | json 0 | xargs xdg-open # Linux

# direct file access? no prob:

$ json package.json bin.json
'bin/json'

$ json file.json subobject.another_subobject.subarray.2
'wow this is inside of an array'

# pretty printing too!

$ json package.json
{
  name: '@slicey/json',
  description: 'Quickly access JSON from stdin.',
...

# works with stdin also:

$ cat mysteries.json | json
[
  {
    created_at: '2009-01-05',
    text: 'Where\'s my Cup Noodles?'
  },
  {
    created_at: '2009-01-06',
    text: 'My Cup Noodles have arms?'
  }
...
```

## motivation

bored on a thursday
