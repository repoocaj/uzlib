# ---------------------------------------------------------------- PROJECT NAME
set(LOCAL_PROJ_NAME uzlib)

# -------------------------------------------------------------- FIND SRC FILES
if(${CMAKE_SYSTEM_PROCESSOR} MATCHES Arm)
    set(CSRC
        src/adler32.c
        src/crc32.c
        src/defl_static.c
        src/genlz77.c
        src/tinfgzip.c
        src/tinflate.c
        src/tinfzlib.c
    )
endif()

# ---------------------------------------------------------------- DEFINE BUILD
if(${CMAKE_SYSTEM_PROCESSOR} MATCHES Arm)

    # Add library
    add_library(${LOCAL_PROJ_NAME} STATIC ${CSRC})

    # Add include paths
    target_include_directories(${LOCAL_PROJ_NAME}
        PUBLIC
            ${CMAKE_CURRENT_LIST_DIR}/src
    )
endif()

