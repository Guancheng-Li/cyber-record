# cyber-record
Pure python code for cyber-record reader/writer, build with bazel
Based on cyber-record 0.1.12 and extracted from whl, you can use `pip install cyber-record` if it is still works well with your protobuf version.

# Why add this repo?
1. The official cyber record reader from Apollo is based on C++ and needs apollo build environment to run, which is not convenient for users who are not familiar with Apollo.
2. The third-party cyber-record which is pure python code is not updated for a long time(2022, 0.1.12), and it limits the protobuf version 3.19.4, which blocks my development.
- So I need a light-weighted cyber-record reader/writer which is pure python code and can be used in any environment.
- I did not make it as a whl because I want make it flexible for different protobuf version, some APIs needs to be modified accord to your protobuf version.

# How to use?
- With bazel:
1. Install bazel, and also prepare yoru `WORKSPACE` file, and `requlirements.txt`;
2. Clone this repo, copy the `cyber_record` folder to your project;
3. Build with bazel;
- Without bazel:
1. Clone this repo, copy the `cyber_record` folder to your project;
2. Install protobuf: `pip install protobuf`;
3. Install use protoc update pb2.py, and replace the one in repo: `protoc --python_out=. *.proto`;

# Update log:
## Date 2025.05.24，Version 0.1.12
1. Based on cyber-record 0.1.12 and extracted from whl;
2. Added `BUILD` files for bazel;
3. Added `proto` files from project Apollo to replace the `pb2.py` files (verified with libprotoc 28.3, generated `pb2.py` keep unchanged); 
6. Removed useless not referenced `.py` files;
7. Removed useless `.pyc` files;
8. Formated code with black-formatter;
