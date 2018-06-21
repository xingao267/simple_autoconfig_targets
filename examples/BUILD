licenses(["notice"])  # Apache 2.0

package(default_visibility = ["//visibility:public"])

load("@bazel_toolchains//rules:docker_config.bzl", "docker_toolchain_autoconfig")
load(
    "@bazel_toolchains//container/rules:docker_toolchains.bzl",
    "toolchain_container",
)

# Simple docker_toolchain_autoconfig target.
docker_toolchain_autoconfig(
    name = "autoconfig",
    base = "@ubuntu16_04-clang//image",
    bazel_version = "0.14.1",
    env = {
        "ABI_VERSION": "clang",
        "ABI_LIBC_VERSION": "glibc_2.19",
        "BAZEL_COMPILER": "clang",
        "BAZEL_HOST_SYSTEM": "i686-unknown-linux-gnu",
        "BAZEL_TARGET_LIBC": "glibc_2.19",
        "BAZEL_TARGET_CPU": "k8",
        "BAZEL_TARGET_SYSTEM": "x86_64-unknown-linux-gnu",
        "CC_TOOLCHAIN_NAME": "linux_gnu_x86",
        "CC": "clang",
    },
    packages = [
        "bazel",
        "ca-certificates-java",
        "curl",
        "git",
        "openjdk-8-jdk-headless",
        "openjdk-8-jre-headless",
        "python-dev",
        "unzip",
        "wget",
        "zip",
    ],
    additional_repos = [
        "deb [arch=amd64] http://storage.googleapis.com/bazel-apt stable jdk1.8"
    ],
    keys = [
        "@bazel_gpg//file",
    ],
    tags = ["manual"],
)

# Simple toolchain_container target.
toolchain_container(
    name = "toolchain",
    base = "@ubuntu16_04//image",
    cmd = [
        "/bin/sh",
        "-c",
        "/bin/bash",
    ],
    env = {
        "LANG": "C.UTF-8",
        "LANGUAGE": "C.UTF-8",
        "LC_ALL": "C.UTF-8",
    },
    packages = [
        "binutils",
        "ca-certificates",
        "curl",
        "ed",
        "file",
        "git",
        "less",
        "locales",
        "locales-all",
        "netcat",
        "openssh-client",
        "patch",
        "unzip",
        "wget",
        "zip",
    ],
)
