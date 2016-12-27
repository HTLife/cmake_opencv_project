cmake_minimum_required(VERSION 2.8)

 project(OpenImage) 
    MACRO(MY_DEFINE_EXAMPLE name srcs) 
        add_executable(${name} ${srcs}) 

        # 設定 include path 
        include_directories("." 
                                                         "C:\\opencv\\build\\include" 
                                                         "C:\\opencv\\build\\include\\opencv" 
                                                         "C:\\opencv\\build\\include\\opencv2") 

        # 設定 library path (自己編譯出來的 OpenCV library 位置) 
        set(MYLIBPATH "C:\\opencv\\build\\x64\\vc14\\lib\\") 
        target_link_libraries(${name} ${MYLIBPATH}opencv_world320d.lib)

       # 使用 Unicode 
        add_definitions(-DUNICODE -D_UNICODE) 
    ENDMACRO(MY_DEFINE_EXAMPLE)


    MY_DEFINE_EXAMPLE(DisplayImage     DisplayImage.cpp)