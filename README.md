# catch2_bazel
Bazel support for catch2

(*Note*: This is 100% based off of [PlacidBox/catch-bazel](https://github.com/PlacidBox/catch-bazel). All credit to [PlacidBox](https://github.com/PlacidBox/). I initially wanted to update that library with the newest catch, but then realized a new repository was needed so bazel could target either version of catch).

Exposes the [Catch2](https://github.com/catchorg/Catch2) testing framework to
[Bazel](https://bazel.build/).

Add this to your `WORKSPACE` file:

```py
http_archive(
    name = "catch2",
    url = "https://github.com/evanmoran/catch2-bazel/archive/v2.2.3.tar.gz",
    strip_prefix = "catch-bazel-2.2.3",
)
```

Then add `@catch2//:main` to the `deps` on `cc_test` rules, like:

```py
cc_test(
    name = "my_test",
    srcs = ["my_test.cpp"],
    deps = ["@catch//:main"],
)
```

Use `@catch2//:catch2` as your dependency  if you need to [write your own main](https://github.com/philsquared/Catch/blob/master/docs/own-main.md#let-catch-take-full-control-of-args-and-config).
This target only exposes the `catch2.hpp` header.

See the [PlacidBox example project](https://github.com/PlacidBox/catch-bazel-example) for code-in-action in catch 1.X.Y versions.



