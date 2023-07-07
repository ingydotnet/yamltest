YAMLTest
========

Write tests in YAMLScript

## Synopsis

A file `test/test.t`:
```
#!/usr/bin/env yamltest

tests =: !
- in:  Oh, hello
  up:  OH, HELLO
  low: oh, hello
- in:  I like Pie!
  up:  I LIKE PIE!
  low: i like pie!
- in:  Ready, Set, Go.
  up:  READY, SET, GO.
  low: ready, set, go.

- for [test tests]:
    is:
    - get(test "in)->toUpperCase()
    - 
```

Run `prove t/test.t`:

```
test/test.t ..
1..8
ok 1 - This test will always 'pass'
not ok 2 # TODO & SKIP Testing 'todo'
# NOTE: This is awesome
ok 3 - Testing 'ok'
# This is a WARNING!
ok 4 - 2 + 2 'is' 4
ok 5 - 2 + 2 'isnt' 5
ok 6 - Testing 'like'
ok 7 - Testing 'unlike'
ok 8 # skip Skipping - Highway to the danger zone
ok
All tests successful.
Files=1, Tests=8,  0 wallclock secs ( 0.02 usr  0.01 sys +  0.12 cusr  0.02 csys =  0.17 CPU)
Result: PASS
```

## Description

YAMLTest let's you write tests in YAML/YAMLScript.

Just add this shebang line to a `test/test-file.t`:

```
#!/usr/bin/env yamltest
```

## See Also:

* [Test::More::YAMLScript](https://metacpan.org/pod/Test::More::YAMLScript)
* [YAMLScript](https://metacpan.org/pod/YAMLScript)
* [Lingy](https://metacpan.org/pod/Lingy)


## Authors

* Ingy döt Net <ingy@ingy.net>


## Copyright and License

Copyright 2022-2023 by Ingy döt Net

This library is free software and may be distributed under the same terms as
perl itself.
