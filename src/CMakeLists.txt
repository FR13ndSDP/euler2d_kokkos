add_executable(euler2d
  ../config/inih/ini.h
  ../config/inih/ini.cpp
  ../config/inih/INIReader.h
  ../config/inih/INIReader.cpp
  ../config/ConfigMap.h
  ../config/ConfigMap.cpp
  kokkos_shared.h
  real_type.h
  HydroParams.h
  HydroParams.cpp
  HydroRun.h
  HydroRun.cpp
  hydro_common.h
  HydroBaseFunctor.h
  HydroRunFunctors.h
  Timer.h
  SimpleTimer.h
  SimpleTimer.cpp
  CudaTimer.h
  main.cpp)

target_include_directories(euler2d
  PUBLIC
  ${CMAKE_SOURCE_DIR})
target_link_libraries(euler2d Kokkos::kokkos HDF5::HDF5)

configure_file(test_blast.ini test_blast.ini COPYONLY)
configure_file(test_blast_large.ini test_blast_large.ini COPYONLY)
configure_file(test_implode.ini test_implode.ini COPYONLY)
configure_file(test_implode_big.ini test_implode_big.ini COPYONLY)
