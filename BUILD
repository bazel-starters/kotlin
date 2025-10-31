"""Targets in the repository root"""

# We prefer BUILD instead of BUILD.bazel
# gazelle:build_file_name BUILD

load("@gazelle//:def.bzl", "gazelle")

exports_files(
    [
        "ktlint-baseline.xml",
        ".editorconfig",
    ],
    visibility = ["//:__subpackages__"],
)

gazelle(
    name = "gazelle",
    env = {
        "ENABLE_LANGUAGES": ",".join([
            "starlark",
            "proto",
            "kotlin",
        ]),
    },
    gazelle = "@multitool//tools/gazelle",
)
