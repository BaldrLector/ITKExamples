cmake_minimum_required(VERSION 3.10.2)

project( IsPixelInsideRegion )

find_package( ITK REQUIRED )
include( ${ITK_USE_FILE} )

add_executable( IsPixelInsideRegion Code.cxx )
target_link_libraries( IsPixelInsideRegion ${ITK_LIBRARIES} )

install( TARGETS IsPixelInsideRegion
  DESTINATION bin/ITKExamples/Core/Common
  COMPONENT Runtime
)

install( FILES Code.cxx CMakeLists.txt
  DESTINATION share/ITKExamples/Code/Core/Common/IsPixelInsideRegion
  COMPONENT Code
)

enable_testing()
add_test( NAME IsPixelInsideRegionTest
  COMMAND ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/IsPixelInsideRegion )
