package(default_visibility = ["//visibility:public"])

licenses(["notice"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_library(
    name = "go_default_library",
    srcs = [
        "doc.go",
        "procfs.go",
        "procfs_fake.go",
        "procfs_linux.go",
    ],
    tags = ["automanaged"],
    deps = [
        "//vendor:github.com/golang/glog",
        "//vendor:k8s.io/apimachinery/pkg/util/errors",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["procfs_linux_test.go"],
    data = [
        "example_proc_cgroup",
    ],
    library = ":go_default_library",
    tags = [
        "automanaged",
    ],
    deps = ["//vendor:github.com/stretchr/testify/assert"],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
)
