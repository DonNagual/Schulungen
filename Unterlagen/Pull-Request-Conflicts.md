```Bash
cmake_minimum_required(VERSION 3.15 FATAL_ERROR)
project(ws
        LANGUAGES CXX
        VERSION 1.1.1)

include(FetchContent)

# nlohmann_json
if (NOT nlohmann_json_FOUND)
<<<<<<< crowCpp_DLL
        include(FetchContent)
        FetchContent_Declare(
                nlohmann_json
                GIT_REPOSITORY https://github.com/nlohmann/json
                GIT_TAG v3.11.3
        )
        FetchContent_MakeAvailable(nlohmann_json)
=======
	FetchContent_Declare(
		nlohmann_json
		GIT_REPOSITORY https://github.com/nlohmann/json
		GIT_TAG	v3.11.3
	)
	FetchContent_MakeAvailable(nlohmann_json)
>>>>>>> master
endif()

# Crow
if (NOT Crow_FOUND)
<<<<<<< crowCpp_DLL
        include(FetchContent)
        FetchContent_Declare(
                Crow
                GIT_REPOSITORY https://github.com/CrowCpp/Crow
                GIT_TAG v1.1.0
        )
        FetchContent_MakeAvailable(Crow)
=======
	FetchContent_Declare(
		Crow
		GIT_REPOSITORY https://github.com/CrowCpp/Crow
		GIT_TAG v1.1.0
	)
	FetchContent_MakeAvailable(Crow)
>>>>>>> master
endif()

add_executable(${PROJECT_NAME} ws.cpp)

target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_20)

target_link_libraries(${PROJECT_NAME} PUBLIC Crow::Crow)
target_link_libraries(${PROJECT_NAME} PUBLIC nlohmann_json::nlohmann_json)
target_link_libraries(${PROJECT_NAME} PUBLIC fmt)

set(BUILD_SHARED_LIBS ON)

# Create the output directory if it doesn`t exist
file(MAKE_DIRECTORY "${CMAKE_BINARY_DIR}/../dynamicLibraries")

# Add a  sawtooth libary to the project
add_library(sawtooth_one SHARED sensorDataGenerator/src/sawtooth_one.cpp)
target_link_libraries(sawtooth_one fmt)
target_compile_definitions(sawtooth_one PRIVATE UADI_EXPORTS)
target_compile_features(sawtooth_one PUBLIC cxx_std_20)

# Set the output directory for the shared libary
set_target_properties(sawtooth_one PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/../dynamicLibraries"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/../dynamicLibraries"
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/../dynamicLibraries"
    )

# Add a  sawtooth libary to the project
add_library(sawtooth_two SHARED sensorDataGenerator/src/sawtooth_two.cpp)
target_link_libraries(sawtooth_two fmt)
target_compile_definitions(sawtooth_two PRIVATE UADI_EXPORTS)
target_compile_features(sawtooth_two PUBLIC cxx_std_20)

# Set the output directory for the shared libary
set_target_properties(sawtooth_two PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/../dynamicLibraries"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/../dynamicLibraries"
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/../dynamicLibraries"
    )

install(TARGETS sawtooth_one DESTINATION lib)
install(TARGETS sawtooth_two DESTINATION lib)

install(FILES dynamicLibraries/sawtooth_one.hpp DESTINATION include)
install(FILES dynamicLibraries/sawtooth_two.hpp DESTINATION include)
```

[zurück](../Commits-and-Pull-Requests.md)
