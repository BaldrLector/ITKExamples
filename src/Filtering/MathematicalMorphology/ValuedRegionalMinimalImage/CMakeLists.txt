cmake_minimum_required(VERSION 3.10.2)

project(ValuedRegionalMinimalImage)

find_package(ITK REQUIRED)
include(${ITK_USE_FILE})


add_executable(ValuedRegionalMinimalImage Code.cxx)
target_link_libraries(ValuedRegionalMinimalImage ${ITK_LIBRARIES})

install(TARGETS ValuedRegionalMinimalImage
  DESTINATION bin/ITKExamples/Filtering/MathematicalMorphology
  COMPONENT Runtime
  )

install(FILES Code.cxx CMakeLists.txt
  DESTINATION share/ITKExamples/Code/Filtering/MathematicalMorphology/ValuedRegionalMinimalImage/
  COMPONENT Code
  )


enable_testing()
add_test(NAME ValuedRegionalMinimalImageTest
  COMMAND ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/ValuedRegionalMinimalImage)

