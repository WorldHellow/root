############################################################################
# CMakeLists.txt file for building ROOT montecarlo/pythia8 package
# @author Pere Mato, CERN
############################################################################

include_directories(${PYTHIA8_INCLUDE_DIR})

ROOT_GENERATE_DICTIONARY(G__EGPythia8 *.h MODULE EGPythia8 LINKDEF LinkDef.h DEPENDENCIES EG Graf VMC Physics)

ROOT_ADD_CXX_FLAG(CMAKE_CXX_FLAGS -Wno-overloaded-virtual)
ROOT_ADD_CXX_FLAG(CMAKE_CXX_FLAGS -Wno-misleading-indentation)

ROOT_LINKER_LIBRARY(EGPythia8 *.cxx G__EGPythia8.cxx LIBRARIES Core ${PYTHIA8_LIBRARIES} DEPENDENCIES EG Graf VMC Physics)
ROOT_INSTALL_HEADERS()
