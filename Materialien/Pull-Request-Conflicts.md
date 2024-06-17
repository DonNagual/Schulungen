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
```

[zurück](../Unterlagen/Commits-and-Pull-Requests.md)
