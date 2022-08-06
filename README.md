# Ar-Cpp

A c++ / cpp implementation of .a and .ar file extraction. A header only library. Also supports .deb unpacking (since deb is an ar file)

Sample usage:

```c++
#include <ar/ar.hpp>
#include <fstream>
#include <iostream>

using namespace std;

int main() {
	//use your own file
	string filename = "../sample.deb";
	ar::Reader r(filename);
	auto stream = r.open("debian-binary");
	cout << "debian-binary = " << stream.rdbuf() << endl;
	return 0;
}
```

The makefile will build and run the main file. (modify the main file to try out the library)


To use this project with a dependency manager install the cpp-dependency-manager project from https://github.com/TAR-ALEX/Cpp-Dependency-Manager.git

and create a vendor.txt file and add the following entries:

```
git "https://github.com/TAR-ALEX/Ar-Cpp" main "./include" "./vendor/include",
git "https://github.com/TAR-ALEX/io_tools.git" master "./include" "./vendor/include",

```
