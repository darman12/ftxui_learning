cmake_minimum_required(VERSION 3.31)
project(ftxui_learning)

set(CMAKE_CXX_STANDARD 23)

# --- Fetch FTXUI -------------------------------------------------------------
include(FetchContent)

set(FETCHCONTENT_UPDATES_DISCONNECTED ON)
set(FETCHCONTENT_QUIET OFF)

FetchContent_Declare(ftxui
        GIT_REPOSITORY https://github.com/ArthurSonzogni/FTXUI
        GIT_TAG v6.1.9  # Replace with a version, tag, or commit hash
)

FetchContent_MakeAvailable(ftxui)
# -----------------------------------------------------------------------------

add_executable(ftxui_learning main.cpp)
target_link_libraries(ftxui_learning
        PRIVATE ftxui::screen
        PRIVATE ftxui::dom
        PRIVATE ftxui::component
)