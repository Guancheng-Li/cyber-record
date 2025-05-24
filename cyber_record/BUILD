load("@rules_python//python:defs.bzl", "py_binary", "py_library")
load("@python_deps//:requirements.bzl", "requirement")


package(default_visibility=["//visibility:public"])


py_library(
    name = "chunk",
    srcs = ["chunk.py"],
    deps = [
        "//cyber_record/cyber/proto:record_py_proto",
    ],
)

py_library(
    name = "common",
    srcs = ["common.py"],
)

py_library(
    name = "logger",
    srcs = ["logger.py"],
)

py_library(
    name = "main",
    srcs = ["main.py"],
    deps = [
        ":record",
        "//cyber_record/cyber/proto:proto_desc_py_proto",
        "//cyber_record/cyber/proto:record_py_proto",
        requirement("protobuf"),
    ],
)

py_library(
    name = "reader",
    srcs = ["reader.py"],
    deps = [
        ":common",
        ":record_exception",
        "//cyber_record/cyber/proto:proto_desc_py_proto",
        "//cyber_record/cyber/proto:record_py_proto",
        "//cyber_record/file_object:chunk",
        requirement("protobuf"),
    ],
)

py_library(
    name = "record_exception",
    srcs = ["record_exception.py"],
)

py_library(
    name = "record",
    srcs = ["record.py"],
    deps = [
        ":common",
        ":reader",
        ":writer",
        "//cyber_record/cyber/proto:record_py_proto",
    ],
)

py_library(
    name = "writer",
    srcs = ["writer.py"],
    deps = [
        ":common",
        "//cyber_record/cyber/proto:proto_desc_py_proto",
        "//cyber_record/cyber/proto:record_py_proto",
        "//cyber_record/file_object:chunk",
        requirement("protobuf"),
    ],
)
