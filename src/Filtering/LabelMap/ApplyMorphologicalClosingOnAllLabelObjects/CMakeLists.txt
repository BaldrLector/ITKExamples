cmake_minimum_required(VERSION 3.10.2)
project( ApplyMorphologicalClosingOnAllLabelObjects )

find_package( ITK REQUIRED )
include( ${ITK_USE_FILE} )

add_executable( ApplyMorphologicalClosingOnAllLabelObjects Code.cxx )
target_link_libraries( ApplyMorphologicalClosingOnAllLabelObjects ${ITK_LIBRARIES} )

install( TARGETS ApplyMorphologicalClosingOnAllLabelObjects
  DESTINATION bin/ITKExamples/Filtering/LabelMap
  COMPONENT Runtime
  )

install( FILES Code.cxx CMakeLists.txt
  DESTINATION share/ITKExamples/Code/Filtering/LabelMap/ApplyMorphologicalClosingOnAllLabelObjects
  COMPONENT Code
  )

enable_testing()
add_test( NAME ApplyMorphologicalClosingOnAllLabelObjectsTest
  COMMAND ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/ApplyMorphologicalClosingOnAllLabelObjects
    ${CMAKE_CURRENT_BINARY_DIR}/2th_cthead1.png
    Output.png
    1
)
