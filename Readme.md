Notes C++
=================

## reference books

*  Beginning C++ Programming ( Richard Grimes )
*  C++ Fundamentals  ( Francesco Zoffoli, Antonio Mallia )


## code examples


## setup

* All examples are compile with mingw-w64  (gcc version 8.1.0)

### Visual Studio Code (configure IntelliSense)

* reference:  https://code.visualstudio.com/docs/cpp/config-mingw

* install vscode, extensions and mingw-w64
* press Cntrl + Shilf + P , start Typing `C/C++` and choose `Edit Configuration`
    * this create the file c_cpp_properties.json
* in compilerPath choose path to g++.exe of mingw-w64
    * example: ` "compilerPath": C:\\mingw-w64\\mingw64\\bin\\g++.exe`
* in intelliSenseMode change to "gcc-x64"
* MORE: build task and debugging


### vscode (configure Debug)

* Press Cntrl + Shilt + P, and type `Debug: Open launch.json`
* Choose `GDB/LLDB` and `default configuration`
* In launch.json
    * set program, example `"program": "${workspaceFolder}\\hello.exe"`
    * set debugger, example : `"miDebuggerPath": "C:\\mingw-w64\\mingw64\\bin\\gdb.exe"`
    * (optional) vscode add a breakpoint to the first line of main, to use it breakpoint : `"stopAtEntry": true`
    * (optional) to run the program in an external console : `"externalConsole": true`

* **IMPORTANT** : to build a debug type executable with CMAKE is required add this line in `CMakeLists.txt`

```
set(CMAKE_BUILD_TYPE Debug)
```


### Compile

* compile file

```
g++ -o hello hello.cpp
```

### compilation process

```
hello.cpp -----> |C++ PreProcessor| -----> temporary file; -----
        [source file]  |
                       |
                       #include header 
                       files

----> |Compiler| ---> Hello.s ----> |Assambler| ---> hello.o  ---
                    [Assembler File]                    [Object file]


----> |Linker| ------> hello.exe
        |                   [executable file]
        |
        Object Code for 
        library functions

```
