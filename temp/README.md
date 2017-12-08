by http://sonseungha.tistory.com/372

## CMAKE_MINIMUM_REQUIRED()
### [문법]

	cmake_minimum_required(VERSION major.minor[.patch[.tweak]] 
		[FATAL_ERROR])

	CMakeLists.txt 파일에 가장 먼저 호출되어야 하는 명령어로, Project name을 명시하는 project() 명령보다 먼저 호출된다. Cmake build를 실행하기 위한 최소 버전을 명시하여 만약 CMake의 현재 버전이 cmake_minimum_required()에 명시된 버전보다 낮다면 build진행을 멈추고 에러를 출력한다.


