load("@io_bazel_rules_go//proto:def.bzl", "go_grpc_library")
load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "a_bit_of_everything.pb.go",
        "a_bit_of_everything.pb.gw.go",
        "echo_service.pb.go",
        "echo_service.pb.gw.go",
        "flow_combination.pb.go",
        "flow_combination.pb.gw.go",
        "stream.pb.go",
        "stream.pb.gw.go",
    ],
    importpath = "github.com/grpc-ecosystem/grpc-gateway/examples/examplepb",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/github.com/golang/protobuf/ptypes/empty:go_default_library",
        "//vendor/github.com/golang/protobuf/ptypes/timestamp:go_default_library",
        "//vendor/github.com/grpc-ecosystem/grpc-gateway/examples/sub:go_default_library",
        "//vendor/github.com/grpc-ecosystem/grpc-gateway/examples/sub2:go_default_library",
        "//vendor/github.com/grpc-ecosystem/grpc-gateway/runtime:go_default_library",
        "//vendor/github.com/grpc-ecosystem/grpc-gateway/third_party/googleapis/google/api:go_default_library",
        "//vendor/github.com/grpc-ecosystem/grpc-gateway/utilities:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/grpc:go_default_library",
        "//vendor/google.golang.org/grpc/codes:go_default_library",
        "//vendor/google.golang.org/grpc/grpclog:go_default_library",
    ],
)

proto_library(
    name = "examplepb_proto",
    srcs = [
        "a_bit_of_everything.proto",
        "echo_service.proto",
        "flow_combination.proto",
        "stream.proto",
    ],
    visibility = ["//visibility:public"],
    deps = [
        "//examples/examplepb:examplepb_proto",
        "//examples/sub:sub_proto",
        "//examples/sub2:sub2_proto",
        "//google/api:api_proto",
        "@com_google_protobuf//:empty_proto",
        "@com_google_protobuf//:timestamp_proto",
    ],
)

go_grpc_library(
    name = "examplepb_go_proto",
    importpath = "github.com/grpc-ecosystem/grpc-gateway/examples/examplepb",
    proto = ":examplepb_proto",
    visibility = ["//visibility:public"],
    deps = [
        "//examples/examplepb:go_default_library",
        "//examples/sub:go_default_library",
        "//examples/sub2:go_default_library",
        "//google/api:go_default_library",
        "@com_github_golang_protobuf//ptypes/empty:go_default_library",
        "@com_github_golang_protobuf//ptypes/timestamp:go_default_library",
    ],
)
