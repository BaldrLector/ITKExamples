cmake_minimum_required(VERSION 3.10.2)

project(ComputePCAShapeFromSample)

find_package(ITK REQUIRED)
include(${ITK_USE_FILE})


add_executable(ComputePCAShapeFromSample Code.cxx)
target_link_libraries(ComputePCAShapeFromSample ${ITK_LIBRARIES})

install(TARGETS ComputePCAShapeFromSample
  DESTINATION bin/ITKExamples/Filtering/ImageStatistics
  COMPONENT Runtime
  )

install(FILES Code.cxx CMakeLists.txt
  DESTINATION share/ITKExamples/Code/Filtering/ImageStatistics/ComputePCAShapeFromSample/
  COMPONENT Code
  )


enable_testing()
add_test(NAME ComputePCAShapeFromSampleTest
  COMMAND ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/ComputePCAShapeFromSample)
