YAMLTest
========

Write tests in YAMLScript

## Synopsis

A file `test/test.yt`:
```
#!/usr/bin/env yamltest

- plan: 8

- pass: This test will always 'pass'

- todo:
  - Testing 'todo'
  - fail: This test will always 'fail'

- note: "NOTE: This is awesome"

- diag: This is a WARNING!

- ok:
  - true
  - Testing 'ok'

- is:
  - add: [2, 2]
  - 4
  - 2 + 2 'is' 4

- isnt:
  - add: [2, 2]
  - 5
  - 2 + 2 'isnt' 5

- like:
  - I like pie!
  - /\blike\b/
  - Testing 'like'

- unlike:
  - Please like me on Facebook
  - /\bunlike\b/
  - Testing 'unlike'

- skip:
  - Skipping - Highway to the danger zone
  - danger: zone
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

You just add this shebang line to a `test/test-file.yt`:
```
#!/usr/bin/env yamltest
```

## Authors

* Ingy döt Net <ingy@ingy.net>

## Copyright and License

Copyright 2022 by Ingy döt Net

This library is free software and may be distributed under the same terms as
perl itself.
