package(default_visibility = ["//visibility:public"])

INSECURE_CIPHER_FACTORY = [
    "src/org/eclipse/jgit/transport/InsecureCipherFactory.java",
]

SRCS = glob(
    ["src/**"],
    exclude = INSECURE_CIPHER_FACTORY,
)

RESOURCES = glob(["resources/**"])

java_library(
    name = "jgit",
    srcs = SRCS,
    resource_strip_prefix = "org.eclipse.jgit/resources",
    resources = RESOURCES,
    deps = [
        ":insecure_cipher_factory",
        "@httpclient//jar",
        "@javaewah//jar",
        "@jsch//jar",
        "@log_api//jar",
        "@servlet_api_3_1//jar",
    ],
)

java_library(
    name = "insecure_cipher_factory",
    srcs = INSECURE_CIPHER_FACTORY,
    javacopts = ["-Xep:InsecureCryptoUsage:OFF"],
)
