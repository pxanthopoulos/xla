load("@tsl//tsl/platform:rules_cc.bzl", "cc_library")
load("//xla/tsl:tsl.bzl", "internal_visibility")
load("//xla/tsl:tsl.default.bzl", "tsl_grpc_cc_dependencies")

package(
    # copybara:uncomment default_applicable_licenses = ["//tensorflow:license"],
    default_visibility = internal_visibility([
        "//xla/tsl:internal",
    ]),
    licenses = ["notice"],
)

cc_library(
    name = "grpc_coordination_client",
    srcs = ["grpc_coordination_client.cc"],
    hdrs = ["grpc_coordination_client.h"],
    deps = [
        "//xla/tsl/distributed_runtime:call_options",
        "//xla/tsl/distributed_runtime/coordination:coordination_client",
        "//xla/tsl/distributed_runtime/rpc:grpc_channel",
        "//xla/tsl/distributed_runtime/rpc:grpc_client_cq_tag",
        "//xla/tsl/distributed_runtime/rpc:grpc_state",
        "//xla/tsl/distributed_runtime/rpc:grpc_util",
        "@tsl//tsl/platform:mutex",
        "@tsl//tsl/platform:protobuf",
        "@tsl//tsl/platform:status",
        "@tsl//tsl/platform:thread_annotations",
        "@tsl//tsl/protobuf:coordination_service_proto_cc",
    ],
)

cc_library(
    name = "grpc_coordination_service_impl",
    srcs = ["grpc_coordination_service_impl.cc"],
    hdrs = ["grpc_coordination_service_impl.h"],
    deps = [
        "//xla/tsl/distributed_runtime/coordination:coordination_service_agent",
        "//xla/tsl/distributed_runtime/coordination:coordination_service_rpc_handler",
        "//xla/tsl/distributed_runtime/rpc:async_service_interface",
        "//xla/tsl/distributed_runtime/rpc:grpc_call",
        "//xla/tsl/distributed_runtime/rpc:grpc_util",
        "@tsl//tsl/platform:env",
        "@tsl//tsl/platform:mutex",
        "@tsl//tsl/platform:thread_annotations",
        "@tsl//tsl/protobuf:coordination_service_cc_grpc_proto",
        "@tsl//tsl/protobuf:coordination_service_proto_cc",
    ] + tsl_grpc_cc_dependencies(),
)
