# trade-frame/lib/TFOptions
cmake_minimum_required (VERSION 3.13)

PROJECT(TFOptions)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_COMPILER_ARCHITECTURE_ID, "x64")
#set(CMAKE_EXE_LINKER_FLAGS "--trace --verbose")
#set(CMAKE_VERBOSE_MAKEFILE ON)

set(
  file_h
    Binomial.h
    Bundle.h
    CalcExpiry.h
    Chain.h
    Engine.h
    Formula.h
    IvAtm.h
    Margin.h
    NoRiskInterestRateSeries.h
    Option.h
    PopulateWithIBOptions.h
    Strike.h
  )

set(
  file_cpp
    Binomial.cpp
    Bundle.cpp
    CalcExpiry.cpp
    Chain.cpp
    Engine.cpp
    Formula.cpp
    IvAtm.cpp
    Margin.cpp
    NoRiskInterestRateSeries.cpp
    Option.cpp
    PopulateWithIBOptions.cpp
    Strike.cpp
  )

add_library(
  ${PROJECT_NAME}
  ${file_h}
  ${file_cpp}
  )

target_compile_definitions(${PROJECT_NAME} PUBLIC BOOST_LOG_DYN_LINK )

target_include_directories(
  ${PROJECT_NAME} PUBLIC
    ".."
  )
