"""BUILD definition for the formatter binary

This is in its own package because it has so many loading-time symbols,
we don't want to trigger eager fetches of these for builds that don't want to run format.
"""

load("@aspect_rules_lint//format:defs.bzl", "format_multirun")
load("@rules_java//java:java_binary.bzl", "java_binary")

# gazelle:exclude
package(default_visibility = ["//:__subpackages__"])

java_binary(
    name = "ktfmt",
    main_class = "com.facebook.ktfmt.cli.Main",
    runtime_deps = ["@ktfmt//jar"],
)

format_multirun(
    name = "format",
    kotlin = ":ktfmt",
    starlark = "@buildifier_prebuilt//:buildifier",
)
