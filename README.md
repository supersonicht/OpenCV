# OpenCV
Some random OpenCV programs to do random elementary stuff.
Might help someone someday :P

# How to install OpenCV

1. Open Project Properties from Solution Explorer

2. From topside, click on "Configuration Manager"

3. Click on Win32 which is under Active solution platform

4. Click on <New>

Then click ARM and change it to x64. Then close it.

5. Now go to C/C++>General and beside "Additional Include Directories" paste $(OPENCV_DIR)\include

6. Now go to Linker>General and beside Additional Library Directories paste $(OPENCV_DIR)\x64\vc11\lib

7. In Linker>Input

paste these under Additional Dependencies

opencv_calib3d245.lib
opencv_contrib245.lib
opencv_core245.lib
opencv_features2d245.lib
opencv_flann245.lib
opencv_gpu245.lib
opencv_haartraining_engine.lib
opencv_highgui245.lib
opencv_imgproc245.lib
opencv_legacy245.lib
opencv_ml245.lib
opencv_nonfree245.lib
opencv_objdetect245.lib
opencv_photo245.lib
opencv_stitching245.lib
opencv_superres245.lib
opencv_ts245.lib
opencv_video245.lib
opencv_videostab245.lib

8. Sample Code:

#include "stdafx.h"
#include "opencv2\highgui\highgui.hpp"

using namespace cv;
using namespace std;

int main(int argc, _TCHAR* argv[])
{
	IplImage* img = cvLoadImage("xyz.jpg");
	cvNamedWindow("Example1", CV_WINDOW_AUTOSIZE);
	cvShowImage("Example1", img);
	cvWaitKey(0);
	cvReleaseImage(&img);
	cvDestroyWindow("Example1");
}
 
