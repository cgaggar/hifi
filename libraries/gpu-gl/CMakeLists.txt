# CLIMAX_MERGE_START
# Ideally this should be gpu-gl and android should have gpu-android-gl. Temp name change.
set(TARGET_NAME gpu-gl1)
setup_hifi_library(Concurrent)
link_hifi_libraries(shared gl gpu)
if (UNIX)
    target_link_libraries(${TARGET_NAME} pthread)
endif(UNIX)
GroupSources("src")

target_opengl()
target_nsight()

if (NOT ANDROID)
  target_glew()
endif ()
