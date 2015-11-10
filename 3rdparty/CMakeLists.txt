cmake_minimum_required(VERSION 3.0)

if(NOT EXISTS ${SYSROOT})
    include(ExternalProject)
    
    ExternalProject_Add(
        External_POCO
        URL                 http://pocoproject.org/releases/poco-1.6.1/poco-1.6.1-all.tar.gz
        CMAKE_ARGS          -DCMAKE_INSTALL_PREFIX=${SYSROOT}
                            -DENABLE_DATA_ODBC=OFF
                            -DENABLE_APACHECONNECTOR=OFF
                            -DENABLE_POCODOC=OFF
                            -DENABLE_PDF=OFF
                            -DENABLE_PAGECOMPILER=OFF
                            -DENABLE_PAGECOMPILER_FILE2PAGE=OFF
                            -DENABLE_TESTS=OFF
    )
endif()
