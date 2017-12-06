## ExampleOfCMake

# cmake는 이미 설치되어 있다고 가정한다.


1. 디렉토리는 아래와 같다.

	- test
	  - Demo
	  - Hello


2. 각각의 폴더에 CMakeLists.txt파일을 생성한다.

	- test/CMakeLists.txt
	  - Demo/CMakeLists.txt
	  - Hello/CmakeLists.txt

3. 각각의 CMakeLists.txt는 아래와 같다.

	test/CMakeLists.txt

	# The name of our project is "HELLO". CMakeLists files in this project can
	# refer to the root source directory of the project as ${HELLO_SOURCE_DIR} and
	# to the root binary directory of the project as ${HELLO_BINARY_DIR}.
	cmake_minimum_required(VERSION 2.6)
	project(HELLO)

	
