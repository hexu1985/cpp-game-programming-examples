cmake_minimum_required(VERSION 3.10)
project(Timber VERSION 1.0.0 LANGUAGES CXX)

# 设置C++标准
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 寻找SFML库
find_package(SFML 2.5 COMPONENTS graphics window system REQUIRED)

# 设置包含目录
include_directories(include)

# 添加可执行文件
add_executable(${PROJECT_NAME}
    Timber.cpp
)

# 链接SFML库
target_link_libraries(${PROJECT_NAME}
    sfml-graphics
    sfml-window
    sfml-system
    sfml-audio
)

# 安装目标（可选）
install(TARGETS ${PROJECT_NAME} DESTINATION bin)
