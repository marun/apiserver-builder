load("@io_bazel_rules_go//proto:def.bzl", "go_grpc_library")
load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "control.pb.go",
        "messages.pb.go",
        "payloads.pb.go",
        "services.pb.go",
        "stats.pb.go",
    ],
    importpath = "google.golang.org/grpc/benchmark/grpc_testing",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/grpc:go_default_library",
    ],
)

proto_library(
    name = "grpc_testing_proto",
    srcs = [
        "control.proto",
        "messages.proto",
        "payloads.proto",
        "services.proto",
        "stats.proto",
    ],
    visibility = ["//visibility:public"],
    deps = ["//:apiserver-builder_proto"],
)

go_grpc_library(
    name = "grpc_testing_go_proto",
    importpath = "google.golang.org/grpc/benchmark/grpc_testing",
    proto = ":grpc_testing_proto",
    visibility = ["//visibility:public"],
    deps = ["//:go_default_library"],
)
