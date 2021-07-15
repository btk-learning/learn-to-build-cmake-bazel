# learn-to-build-cmake-bazel
## Building with cmake
We run the commands
```bash
mkdir build && cd build && cmake .. && make
```
In `src/CMakeLists.txt` we include a non-existant directory `path/that/doesnt/exist`, we get the following expected warning
```bash
cc1plus: warning: path/that/doesnt/exist: No such file or directory [-Wmissing-include-dirs]
```
So far the behavior warns for non-existant directories as expected

## Building with bazel
We run the commands
```bash
bazel build //src:main
```
In `src/BUILD.bazel` we include a non-existant directory `path/that/doesnt/exist`. However, when I run this on my Linux machine, I obtain the following missing directories
```bash
cc1plus: warning: path/that/doesnt/exist: No such file or directory [-Wmissing-include-dirs]
cc1plus: warning: bazel-out/k8-fastbuild/bin/external/bazel_tools: No such file or directory [-Wmissing-include-dirs]
```

# Question: Why is this include directory missing?
```
cc1plus: warning: bazel-out/k8-fastbuild/bin/external/bazel_tools: No such file or directory [-Wmissing-include-dirs]
```