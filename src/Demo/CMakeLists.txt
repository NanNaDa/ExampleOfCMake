# Make sure the compiler can find include files from our Hello library.
include_directories(${HELLO_SOURCE_DIR}/Hello)

# Add executable called "helloDemo" that is built from the source files
# "demo.cxx" and "demo_b.cxx". The extensions are automatically found.
add_executable(helloDemo demo.c)

# Link the executable to the Hello library.
target_link_libraries(helloDemo Hello)
