# OpenCV build script for NVIDIA Jetson Nano

This script builds OpenCV from source on Jetson Nano.

This script is untested and expected it to break. Please report breakage 
[here](https://github.com/mdegans/nano_build_opencv/issues).

Related thread on Nvidia developer forum 
[here](https://devtalk.nvidia.com/default/topic/1051133/jetson-nano/opencv-build-script/).

## Usage:
```shell
sh build_opencv.sh $1 $2
```

where:
- __$1__ optional argument: number or tag of OpenCV you want to attempt to build
  (__default 4.1.0__)
- __$2__ optional argument: if "test", runs the test suite (see notes below on that)

## Specifying an OpenCV version (git branch)
```shell
sh build_opencv.sh 4.0.0
```

Where `4.0.0` is any version of openCV from 2.2 to 4.1.0
(any valid OpenCV git branch or tag will also work).

## Running Tests
Becuase the tests consume so much memory, it's recommended to mount an external 
swapfile via usb3 before doing so as otherwise you will swap from your microsd 
card and that will shorten it's lifespan artificially.

If you've done that or are willing to stress your microsd card to test, you can
run the tests by adding "test" as the second argument to the script.

```shell
sh build_opencv.sh 4.0.0 test
```
