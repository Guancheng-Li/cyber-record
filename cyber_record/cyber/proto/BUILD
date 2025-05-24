load("@rules_proto//proto:defs.bzl", "proto_library")
load("@rules_python//python:proto.bzl", "py_proto_library")


package(default_visibility=["//visibility:public"])


proto_library(
    name = "proto_desc_proto",
    srcs = ["proto_desc.proto"],
)

py_proto_library(
    name = "proto_desc_py_proto",
    deps = [":proto_desc_proto"],
)

proto_library(
    name = "record_proto",
    srcs = ["record.proto"],
)

py_proto_library(
    name = "record_py_proto",
    deps = [":record_proto"],
)
