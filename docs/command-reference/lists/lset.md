---
description: Set the value of an element in a list by its index
---

# LSET

## Syntax

    LSET key index element

**Time complexity:** O(N) where N is the length of the list. Setting either the first or the last element of the list is O(1).

Sets the list element at `index` to `element`.
For more information on the `index` argument, see `LINDEX`.

An error is returned for out of range indexes.

## Return

[Simple string reply](https://redis.io/docs/reference/protocol-spec#resp-simple-strings)

## Examples

```shell
dragonfly> RPUSH mylist "one"
(integer) 1
dragonfly> RPUSH mylist "two"
(integer) 2
dragonfly> RPUSH mylist "three"
(integer) 3
dragonfly> LSET mylist 0 "four"
"OK"
dragonfly> LSET mylist -2 "five"
"OK"
dragonfly> LRANGE mylist 0 -1
1) "four"
2) "five"
3) "three"
```
