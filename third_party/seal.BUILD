load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")

filegroup(
    name = "src", 
    srcs = glob(["**"]), 
    visibility = ["//visibility:public"]
)

cmake(
   name = "seal",
   cache_entries = {
        "SEAL_USE_CXX17=ON",
        "SEAL_USE_INTRIN=ON",
        "SEAL_USE_MSGSL=OFF",
        "-DSEAL_USE_ZLIB=OFF",
        "SEAL_BUILD_TESTS=OFF",
        "BUILD_SHARED_LIBS=OFF",
        "CMAKE_BUILD_TYPE=Release",
   },
   #make_commands = [
   #     "make -j",
   #     "make install"
   #],
   lib_source = ":src",
   #install_prefix = "native/src",
   out_include_dir = "include/SEAL-3.5",
   out_static_libs = ["libseal-3.5.a"],
   visibility = ["//visibility:public"],
)
