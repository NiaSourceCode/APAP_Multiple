# 用于多图拼接的APAP

[项目主页](https://cs.adelaide.edu.au/~tjchin/apap/)

主程序:`MDLT_mainImageStitchingNRBA.m`

`mex`文件需要保留

# 编译(没有成功)

[参考: CSDN](https://blog.csdn.net/dreamguard/article/details/84898505)

- eigen

- glog 0.3.4

(下面的命令尽量不要省)

```bash
tar zxvf glog-0.3.4.tar.gz
cd glog-0.3.4
./configure
make
sudo make install
```

- ceres solver 1.6.0

```bash
# google-glog + gflags
sudo apt-get install libgoogle-glog-dev


# BLAS & LAPACK
sudo apt-get install libatlas-base-dev
# Eigen3
sudo apt-get install libeigen3-dev

# SuiteSparse and CXSparse (optional)
# - If you want to build Ceres as a *static* library (the default)
#   you can use the SuiteSparse package in the main Ubuntu package
#   repository:
sudo apt-get install libsuitesparse-dev
# - However, if you want to build Ceres as a *shared* library, you must
#   add the following PPA:
sudo add-apt-repository ppa:bzindovic/suitesparse-bugfix-1319687
sudo apt-get update
sudo apt-get install libsuitesparse-dev


# 依赖项安装完成，安装Ceres
tar zxf ceres-solver-1.3.0.tar.gz
mkdir ceres-bin
cd ceres-bin
cmake ../ceres-solver-1.3.0
make -j3
make test
# Optionally install Ceres, it can also be exported using CMake which
# allows Ceres to be used without requiring installation, see the documentation
# for the EXPORT_BUILD_DIR option for more information.
make install
```
