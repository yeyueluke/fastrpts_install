1.foonathan memory
	$ git clone https://github.com/foonathan/memory.git
	$ cd memory
	$ git submodule update --init --recursive
	$ mkdir build && cd build
	$ cmake -DCMAKE_INSTALL_PREFIX=/usr/local -DBUILD_SHARED_LIBS=ON ..
	$ make; sudo make install

2. gradle

3. openjdk

4. fastrtpsgen
	$ git clone --recursive https://github.com/eProsima/Fast-RTPS-Gen.git
	$ cd Fast-RTPS-Gen
	$ gradle assemble

5.fastrtps
	$ git clone https://github.com/eProsima/Fast-RTPS
	$ cd Fast-RTPS
	$ mkdir build
	$ cd build
	$ cmake -DBUILD_JAVA=ON -DCOMPILE_EXAMPLES=ON -DPERFORMANCE_TESTS=ON -DTHIRDPARTY=ON ..
	$ make
	$ sudo make install

6. test fastrtps
	$ mkdir -p ~/testFastRTPS
	$ cd ~/testFastRTPS
	$ vi HelloWorld.idl
	    struct HelloWorld
		{
		    string msg;
		};
	$ path/Fast-RTPS-Gen/script/fastrtpsgen -example CMake HelloWorld.idl
	$ mkdir build && cd build
	$ cmake ..
	$ make
	$ ./HelloWorld publisher
    another shell:
	$ ./HelloWorld subscriber
