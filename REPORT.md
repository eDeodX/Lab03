# Задание 1

## Вам поручили перейти на систему автоматизированной сборки CMake. Исходные файлы находятся в директории formatter_lib. В этой директории находятся файлы для статической библиотеки formatter. Создайте CMakeLists.txt в директории formatter_lib, с помощью которого можно будет собрать ститческую библиотеку formatter:

Создаём нужные нам для статической библиотеки файлы:

<pre>root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib# mkdir include
root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib# cd include
root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib/include# touch formatter.h
root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib/include# subl formatter.h
root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib/include# cd ..
root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib# mkdir sources
root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib# cd sources
root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib/sources# touch formatter.cpp
root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib/sources# subl formatter.cpp
</pre>

Создаём CMakeLists.txt:

<pre>root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib# touch CMakeLists.txt
root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib# subl CMakeLists.txt</pre>

<pre>cmake_minimum_required(VERSION 3.4)
project(formatter)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(formatter STATIC ~/eDeodX/workspace/tasks/HM3/formatter_lib/sources/formatter.cpp)
include_directories(~/eDeodX/workspace/tasks/HM3/formatter_lib/include)</pre>

Билдим:

<pre>root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib# cmake -H. -B_build
CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake &lt; 3.10 will be removed from a future version of
  CMake.

  Update the VERSION argument &lt;min&gt; value.  Or, use the &lt;min&gt;...&lt;max&gt; syntax
  to tell CMake that the project requires at least &lt;min&gt; but has been updated
  to work with policies introduced by &lt;max&gt; or earlier.


-- The C compiler identification is GNU 14.2.0
-- The CXX compiler identification is GNU 14.2.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done (0.4s)
-- Generating done (0.0s)
-- Build files have been written to: /root/eDeodX/workspace/tasks/HM3/formatter_lib/_build
root@debian:~/eDeodX/workspace/tasks/HM3/formatter_lib# cmake --build _build
[ 50%] <font color="#00AA00">Building CXX object CMakeFiles/formatter.dir/sources/formatter.cpp.o</font>
[100%] <font color="#55FF55"><b>Linking CXX static library libformatter.a</b></font>
[100%] Built target formatter
</pre>

# Задание 2

##