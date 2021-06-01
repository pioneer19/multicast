project( multicast )
cmake_minimum_required( VERSION 3.8 )

#set( CMAKE_CXX_STANDARD 14 )
#set( CMAKE_CXX_STANDARD_REQUIRED ON )
#set( CMAKE_CXX_EXTENSIONS OFF )

#set( CMAKE_THREAD_PREFER_PTHREAD TRUE )
#set( THREADS_PREFER_PTHREAD_FLAG TRUE )
#find_package( Threads REQUIRED)
# this works with only cmake 3.1.0+
#target_link_libraries( my_app Threads::Threads )
# set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

if( MSVC )
    add_compile_options( /W3 /WX )
else()
    add_compile_options( -Wall -Wextra -pedantic -mtune=native -march=native )
endif()

add_executable( listener
    src/listener.c
)
#target_link_libraries( main Threads::Threads )
#target_include_directories( main PRIVATE include )
#target_compile_features( main PUBLIC cxx_std_17 )

add_executable( sender
    src/sender.c
)
