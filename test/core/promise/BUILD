# Copyright 2021 gRPC authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

load("//bazel:grpc_build_system.bzl", "grpc_cc_library", "grpc_cc_test", "grpc_package")
load("//test/core/util:grpc_fuzzer.bzl", "grpc_proto_fuzzer")

licenses(["notice"])

grpc_package(name = "test/core/promise")

grpc_cc_library(
    name = "test_wakeup_schedulers",
    testonly = True,
    hdrs = ["test_wakeup_schedulers.h"],
    external_deps = ["gtest"],
    visibility = ["//test/core:__subpackages__"],
    deps = [
        "//:gpr_base",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "poll_test",
    srcs = ["poll_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:poll",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "context_test",
    srcs = ["context_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:context",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "promise_test",
    srcs = ["promise_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:promise",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "arena_promise_test",
    srcs = ["arena_promise_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:arena_promise",
        "//:resource_quota",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    # Why promise_map_test and not map_test?
    # third_party/benchmark defines a map_test in its cmakefile, and we depend
    # on that from our cmakefile, and cmake wants to have a flat namespace to
    # deal with xcode/visual studio limitations... sooo... promise_map_test it
    # is.
    name = "promise_map_test",
    srcs = ["map_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:map",
        "//:promise",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "race_test",
    srcs = ["race_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:race",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "promise_factory_test",
    srcs = ["promise_factory_test.cc"],
    external_deps = [
        "gtest",
        "absl/functional:bind_front",
    ],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:capture",
        "//:promise",
        "//:promise_factory",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "if_test",
    srcs = ["if_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:if",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "loop_test",
    srcs = ["loop_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:loop",
        "//:seq",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "join_test",
    srcs = ["join_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:join",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "try_join_test",
    srcs = ["try_join_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:try_join",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "seq_test",
    srcs = ["seq_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:seq",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "try_seq_test",
    srcs = ["try_seq_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:try_seq",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "activity_test",
    srcs = ["activity_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "test_wakeup_schedulers",
        "//:activity",
        "//:join",
        "//:promise",
        "//:seq",
        "//:wait_set",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "latch_test",
    srcs = ["latch_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "test_wakeup_schedulers",
        "//:join",
        "//:latch",
        "//:seq",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "observable_test",
    srcs = ["observable_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "test_wakeup_schedulers",
        "//:observable",
        "//:promise",
        "//:seq",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "for_each_test",
    srcs = ["for_each_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "test_wakeup_schedulers",
        "//:for_each",
        "//:join",
        "//:map",
        "//:observable",
        "//:pipe",
        "//:resource_quota",
        "//:seq",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_cc_test(
    name = "pipe_test",
    srcs = ["pipe_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "test_wakeup_schedulers",
        "//:join",
        "//:pipe",
        "//:promise",
        "//:resource_quota",
        "//:seq",
        "//test/core/util:grpc_suppressions",
    ],
)

grpc_proto_fuzzer(
    name = "promise_fuzzer",
    srcs = ["promise_fuzzer.cc"],
    corpus = "promise_fuzzer_corpus",
    language = "C++",
    proto = "promise_fuzzer.proto",
    tags = ["no_windows"],
    uses_polling = False,
    deps = [
        "//:activity",
        "//:join",
        "//:map",
        "//:promise",
        "//:race",
        "//:seq",
        "//test/core/util:grpc_test_util",
    ],
)

grpc_cc_test(
    name = "exec_ctx_wakeup_scheduler_test",
    srcs = ["exec_ctx_wakeup_scheduler_test.cc"],
    external_deps = ["gtest"],
    language = "c++",
    uses_polling = False,
    deps = [
        "//:activity",
        "//:exec_ctx_wakeup_scheduler",
        "//test/core/util:grpc_suppressions",
    ],
)
