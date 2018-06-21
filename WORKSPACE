load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
  name = "bazel_toolchains",
  urls = [
    "https://github.com/bazelbuild/bazel-toolchains/archive/e6b994bf0e5e297cbe68d6499352d18440092bcf.tar.gz",
  ],
  strip_prefix = "bazel-toolchains-e6b994bf0e5e297cbe68d6499352d18440092bcf",
  sha256 = "10d1a65e35c3b3b6d7964b99ab0a87d1be9fcfa71315690809e08606605a020d",
)

load(
    "@bazel_toolchains//repositories:repositories.bzl",
    bazel_toolchains_repositories = "repositories",
)

bazel_toolchains_repositories()

load(
    "@io_bazel_rules_docker//container:container.bzl",
    container_repositories = "repositories",
    "container_pull",
)

container_repositories()

# gcr.io/cloud-marketplace/google/clang-ubuntu:r328903
container_pull(
    name = "ubuntu16_04-clang",
    digest = "sha256:d553634f23f7c437ca35bbc4b6f1f38bb81be32b9ef2df4329dcd36762277bf7",
    registry = "gcr.io",
    repository = "cloud-marketplace/google/clang-ubuntu",
)

container_pull(
    name = "ubuntu16_04",
    digest = "sha256:5125aac627c68226c6ad6083d0e3419bc6252bea1eb9d6e7258ecfd67233d655",
    registry = "gcr.io",
    repository = "cloud-marketplace/google/ubuntu16_04",
)
