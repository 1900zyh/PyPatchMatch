# PyPatchMatch
PyPatchMatch is a Cython wrapper of inpainting technique based on [PatchMatch](https://gfx.cs.princeton.edu/pubs/Barnes_2009_PAR/index.php) for restoring the miss area in an image.  
The porject mainly  based on a C implementation of [PatchMatch](https://github.com/younesse-cv/PatchMatch) and a cython wrapper of [np.array <-> cv::Mat](https://github.com/solivr/cython_opencvMat).  
## Prerequisites
- cmake
- [OpenCV 2.2.0](https://sourceforge.net/projects/opencvlibrary/files/opencv-unix/2.2/OpenCV-2.2.0.tar.bz2/download)
- python 3.5
- cython
- numpy
## Build
- check OpenCV have been built as [the tutorial](https://docs.opencv.org/3.0.0/d7/d9f/tutorial_linux_install.html)
- check [`SYS_PREFIX`](https://github.com/Maktu6/PyPatchMatch/blob/master/setup.py#L11) in `setup.py` is correct path of OpenCV libraries 

To build, run `sh build.sh`.
## Use
**`PyPatchMatch_inpaint(input, mask, radius)`**  
Args:
- input: the original RGB image (a HxWx3 `numpy.array`)
- mask: the miss mask of image, the value in miss area is 1 (a HxW `numpy.array`)
- radius: patch radius

Return:
- the result RGB image (a HxWx3 `numpy.array`)  

[`demo.ipynb`](https://github.com/Maktu6/PyPatchMatch/blob/master/demo.ipynb) is an example of inpainting images via PyPatchMatch.  
