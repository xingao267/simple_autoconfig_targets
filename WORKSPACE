load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# The commit of @bazel_toolchains determines the following things:
# - The version of @io_bazel_rules_docker, @io_bazel_rules_go,
#   @base_images_docker, @distroless, @bazel_gpg.
#
#   If you would like to use a different version of one of the above repos, add
#   a new http_archive or http_file target of it with your desired commit ABOVE
#   this.
http_archive(
    name = "bazel_toolchains",
    sha256 = "9c0217fdc438bbf910adc4c2d6be4cec9b1e1bfe4918c3f7b8d9485b3ef21fe2",
    strip_prefix = "bazel-toolchains-b16e98cf5346748354879e4e52d049194ca72510",
    urls = [
        "https://github.com/bazelbuild/bazel-toolchains/archive/b16e98cf5346748354879e4e52d049194ca72510.tar.gz",
    ],
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
