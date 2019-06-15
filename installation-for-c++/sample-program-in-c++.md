# Sample Program in c++

**Create a C++ program**

```text
$ mkdir cpp_test
 
$ cd cpp_test
 
$ touch main.cpp
```

The above command will create a folder called `cpp_test` and create a `main.cpp` file inside it**.**Now place any `.jpeg` image inside the `cpp_test` folder.So Now your `cpp_test` folder will contain two files as follows

```text
.
├── sample.jpeg
└── main.cpp
```

Now open the main.cpp and add the following code

```text
#include <opencv2/highgui.hpp>
#include <iostream>
 
int main( int argc, char** argv ) {
  
  cv::Mat image;
  image = cv::imread("sample.jpeg" , CV_LOAD_IMAGE_COLOR);
  
  if(! image.data ) {
      std::cout <<  "Could not open or find the image" << std::endl ;
      return -1;
    }
  
  cv::namedWindow( "Display window", cv::WINDOW_AUTOSIZE );
  cv::imshow( "Display window", image );
  
  cv::waitKey(0);
  return 0;
}
```

**Now compile your code with the following command**

```text
$ g++ main.cpp -o output `pkg-config --cflags --libs opencv`
```

```text
$ ./output
```

press ESC to exit

