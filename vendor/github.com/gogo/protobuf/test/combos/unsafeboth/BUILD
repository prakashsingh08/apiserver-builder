load("@io_bazel_rules_go//proto:def.bzl", "go_proto_library")
load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "t.go",
        "thetest.pb.go",
        "uuid.go",
    ],
    importpath = "github.com/gogo/protobuf/test/combos/unsafeboth",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/gogo/protobuf/gogoproto:go_default_library",
        "//vendor/github.com/gogo/protobuf/proto:go_default_library",
        "//vendor/github.com/gogo/protobuf/protoc-gen-gogo/descriptor:go_default_library",
        "//vendor/github.com/gogo/protobuf/sortkeys:go_default_library",
        "//vendor/github.com/gogo/protobuf/test/custom:go_default_library",
        "//vendor/github.com/gogo/protobuf/test/custom-dash-type:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "bug_test.go",
        "thetestpb_test.go",
    ],
    importpath = "github.com/gogo/protobuf/test/combos/unsafeboth",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/gogo/protobuf/gogoproto:go_default_library",
        "//vendor/github.com/gogo/protobuf/jsonpb:go_default_library",
        "//vendor/github.com/gogo/protobuf/proto:go_default_library",
    ],
)

proto_library(
    name = "test_proto",
    srcs = ["thetest.proto"],
    visibility = ["//visibility:public"],
    deps = ["//github.com/gogo/protobuf/gogoproto:gogoproto_proto"],
)

go_proto_library(
    name = "test_go_proto",
    importpath = "github.com/gogo/protobuf/test/combos/unsafeboth",
    proto = ":test_proto",
    visibility = ["//visibility:public"],
    deps = ["//github.com/gogo/protobuf/gogoproto:go_default_library"],
)
