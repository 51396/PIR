load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")

filegroup(
    name = "src", 
    srcs = glob(["**"]), 
    visibility = ["//visibility:public"]
)

cmake(
   name = "seal",
   cmake_entries = [
        "-DSEAL_USE_CXX17=ON",
        "-DSEAL_USE_INTRIN=ON",
        "-DSEAL_USE_MSGSL=OFF",
        "-DSEAL_USE_ZLIB=OFF",
        "-DSEAL_BUILD_TESTS=OFF",
        "-DBUILD_SHARED_LIBS=OFF",
        "-DCMAKE_BUILD_TYPE=Release",
   ],
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
