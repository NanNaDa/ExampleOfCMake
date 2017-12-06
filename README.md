# ExampleOfCMake

## cmake는 이미 설치되어 있다고 가정한다.

<ol>
	<li>디렉토리는 아래와 같다.</li>
	<ul>
		<li>test</li>
		<ul>
			<li>Demo</li>
			<li>Hello</li>
		</ul>
	</ul>
	<li>각각의 폴더에 CMakeLists.txt파일을 생성한다.</li>
	<ul>
		<li>test/CMakeLists.txt</li>
		<ul>
			<li>Demo/CMakeLists.txt</li>
			<li>Hello/CmakeLists.txt</li>
		</ul>
	</ul>
	<li>각각의 CMakeLists.txt는 아래와 같다.</li>

	## test/CMakeLists.txt
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

	## test/Hello/CMakeLists.txt
	# Create a library called "Hello" which includes the source file "hello.cxx"
	#
</ol>

