# C++ extension for fast image processing

It is based on [pybind11_opencv_numpy](https://github.com/edmBernard/pybind11_opencv_numpy).
that allows interpolation between cv::Mat <-> np.array.

Depending on the resize strategy (nearest neighbors or bilinear), the speedup compare to pure python + numpy is between x2 and x6.

## Dependencies

- [PyBind11 2.2.1](https://github.com/pybind/pybind11)
- OpenCV 3 with Eigen support
- [Eigen 3.3](http://eigen.tuxfamily.org/index.php?title=Main_Page)

### Compile with CMake

#### On the rapsberry pi
```
./pi_cmake.sh
```

#### On the Laptop
```bash
mkdir build && cd build
# configure make
cmake ..
# generate the fast_image_processing.so library
make
# move fast_image_processing.so library in current folder
make install
```

### Compile with setup.py
WARNING: you have to manually edit the path to OpenCV + Eigen
```
./compile.sh
```

### Run
To run the test, you need to copy `mlp_model.npz` in this folder and have an image named `test_sun.jpg` (ideally taken from the raspicam).
```bash
python test.py
```
