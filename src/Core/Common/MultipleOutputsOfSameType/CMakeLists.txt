cmake_minimum_required(VERSION 3.10.2)

project(MultipleOutputsOfSameType)

find_package(ITK REQUIRED)
include(${ITK_USE_FILE})


add_executable(MultipleOutputsOfSameType Code.cxx)
target_link_libraries(MultipleOutputsOfSameType ${ITK_LIBRARIES})

install(TARGETS MultipleOutputsOfSameType
  DESTINATION bin/ITKExamples/Core/Common
  COMPONENT Runtime
  )

install(FILES Code.cxx CMakeLists.txt
  DESTINATION share/ITKExamples/Code/Core/Common/MultipleOutputsOfSameType/
  COMPONENT Code
  )


enable_testing()
add_test(NAME MultipleOutputsOfSameTypeTest
  COMMAND ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/MultipleOutputsOfSameType)
