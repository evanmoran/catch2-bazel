
cc_library(
    name = "catch2",
    srcs = ["catch2.hpp"],
    visibility = ["//visibility:public"],
)

cc_library(
    name = "main",
    srcs = ["main.cpp"],
    linkstatic = True,
    visibility = ["//visibility:public"],
    deps = [":catch2"],
    alwayslink = True,
)