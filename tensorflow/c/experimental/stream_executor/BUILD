# Description:
# StreamExecutor C API.

load("//tensorflow/core/platform:rules_cc.bzl", "cc_library")
load(
    "//tensorflow:tensorflow.bzl",
    "tf_cc_test",
)

package(
    licenses = ["notice"],  # Apache 2.0
)

cc_library(
    name = "stream_executor",
    srcs = ["stream_executor.cc"],
    hdrs = ["stream_executor.h"],
    visibility = ["//visibility:public"],
    deps = [
        ":stream_executor_internal",
        "//tensorflow/c:c_api_macros",
        "//tensorflow/c:tf_status",
        "//tensorflow/c:tf_status_helper",
        "//tensorflow/core:lib",
        "//tensorflow/core/platform:regexp",
        "//tensorflow/core/platform:strcat",
        "//tensorflow/stream_executor:executor_cache",
        "//tensorflow/stream_executor:multi_platform_manager",
        "//tensorflow/stream_executor:platform",
        "//tensorflow/stream_executor:stream_executor_internal",
        "//tensorflow/stream_executor:stream_executor_pimpl",
        "//tensorflow/stream_executor:timer",
    ],
)

cc_library(
    name = "stream_executor_internal",
    hdrs = [
        "stream_executor.h",
        "stream_executor_internal.h",
    ],
    deps = [
        "//tensorflow/c:c_api_macros",
        "//tensorflow/c:tf_status",
        "//tensorflow/stream_executor:executor_cache",
        "//tensorflow/stream_executor/lib",
    ],
)

tf_cc_test(
    name = "stream_executor_test",
    srcs = ["stream_executor_test.cc"],
    deps = [
        ":stream_executor",
        ":stream_executor_internal",
        "//tensorflow/core:test",
        "//tensorflow/core:test_main",
        "//tensorflow/core/protobuf:error_codes_proto_impl_cc",
        "//tensorflow/stream_executor:multi_platform_manager",
        "//tensorflow/stream_executor:stream",
        "//tensorflow/stream_executor:stream_executor_pimpl",
    ],
)
