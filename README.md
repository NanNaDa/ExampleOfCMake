# ExampleOfCMake
by http://blog.naver.com/PostView.nhn?blogId=imisehi&logNo=150076922823
## cmake는 이미 설치되어 있다고 가정한다.


## 디렉토리는 아래와 같다.
<ul>
	<li>src</li>
	<ul>
		<li>Demo</li>
		<li>Hello</li>
	</ul>
</ul>
	
## 각각의 폴더에 CMakeLists.txt파일을 생성한다.
<ul>
	<li>src/CMakeLists.txt</li>
	<ul>
		<li>Demo/CMakeLists.txt</li>
		<li>Hello/CmakeLists.txt</li>
	</ul>
</ul>


## 각각의 CMakeLists.txt는 아래와 같다.
#### src/CMakeLists.txt
	# The name of our project is "HELLO". CMakeLists files in this project can
	# refer to the root source directory of the project as ${HELLO_SOURCE_DIR} and 
	# to the root binary directory of the project as ${HELLO_BINARY_DIR}.
	cmake_minimum_required(VERSION 2.6)
	project(HELLO)
	# 
	# Recurse into the "Hello" and "Demo" subdirectories. This does not actually
	# cause another cmake executable to run. The same process will walk through
	# the project's entire directory structure.
	add_subdirectory(Hello)
	add_subdirectory(Demo)

#### src/Hello/CMakeLists.txt
	# Create a library called "Hello" which includes the source file "hello.cxx"
	# The extension is already found. Any number of sources could be listed here.
	add_library(Hello hello.c)

#### src/Demo/CMakeLists.txt
	# Make sure the compiler can find include files from our Hello library.
	include_directories(${HELLO_SOURCE_DIR}/Hello)
	#
	# Make sure the linker can find the Hello library once it is built
	link_directories(${HELLO_BINARY_DIR}/Hello)
	# 
	# Add executable called "helloDemo" that is built from the source files
	# "demo.cxx" and "demo_b.cxx". The extensions are automatically found.
	add_executable(helloDemo demo.c)
	#
	# Link the executable to the Hello library.
	target_link_libraries(helloDemo Hello)

## src/Hello와 src/Demo에 소스코드를 작성한다.
#### src/Demo/demo.c
	#include <stdio.h>
	#include "hello.h"
	int main()
	{
		hello();
		return 0;
	}

#### src/Hello/hello.h
	#include <stdio.h>
	
	#ifndef __HELLO_H__
	#define __HELLO_H__

	void hello();

	#endif

#### src/Hello/hello.c
	#include "hello.h"

	void hello()
	{
		printf("안녕하세요?\n");
	}


## 빌드 (Build)

	$ cmake CMakeLists.txt


## 링크 (Link)

	$ make


## 실행 (Execute)

	$ ./Demo/helloDemo
