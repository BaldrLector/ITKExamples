cmake_minimum_required(VERSION 3.10.2)

project(BinaryORTwoImages)

find_package(ITK REQUIRED)
include(${ITK_USE_FILE})


add_executable(BinaryORTwoImages Code.cxx)
target_link_libraries(BinaryORTwoImages ${ITK_LIBRARIES})

install(TARGETS BinaryORTwoImages
  DESTINATION bin/ITKExamples/Filtering/ImageIntensity
  COMPONENT Runtime
  )

install(FILES Code.cxx CMakeLists.txt
  DESTINATION share/ITKExamples/Code/Filtering/ImageIntensity/BinaryORTwoImages/
  COMPONENT Code
  )


enable_testing()
add_test(NAME BinaryORTwoImagesTest
  COMMAND ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/BinaryORTwoImages)

