NOTE: This project will soon be deprecated.  You can find the same (and more) functionality in the VisualOdometryLib project, under CorrespondenceLib.  I'm leaving this up for now because the other lib does not yet have a non-SSE implementation.


To do an out-of-source build for VS2010:

(Modify the top-level CMakeLists.txt file)
Change the OpenCV_INCLUDE and OpenCV_LIB variables so that they point to your OpenCV installation

(from top-level of the project)
mkdir _bld
cd _bld
cmake -G "Visual Studio 10" ..

Usage: [path/to/image1] [path/to/image2] [Max Hamming Dist] [Max Disparity] [Epipolar Range]

Max Hamming Distance: Filter out bad matches.  The lower this value, the more heavily matches will be filtered.

Max Disparity: For general use, set to about 1/10 of the image width.  If you know you are looking only for depths that are further away, you can tweak this accordingly.  It greatly speeds up matching time.

Epipolar Range: Ideally set to 1, but you can tweak this according to the quality of your calibration.  You can get better results from poorly calibrated pairs if you let this out to 3 or 5.  Increasing it will degrade performance.
