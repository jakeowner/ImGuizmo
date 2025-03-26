project(ImGuizmo)

#set(IMGUIZMO_SRC)
#retrieve_files(${CMAKE_CURRENT_SOURCE_DIR} IMGUIZMO_SRC)
aux_source_directory(. IMGUIZMO_SRC)

#option(ENABLE_BULLET_DEBUG "Enable Bullet Physics Debug Visualization (OpenGL)" ON)
#if(ENABLE_BULLET_DEBUG)
#    add_definitions(-DDebugBullet)
#endif()
find_package(imgui REQUIRED)
add_library(${PROJECT_NAME} ${IMGUIZMO_SRC})

target_include_directories(${PROJECT_NAME} PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}
)

target_link_libraries(${PROJECT_NAME} PUBLIC
        imgui::imgui
)
