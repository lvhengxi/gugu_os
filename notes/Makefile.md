makefile的学习：
$@表示目标
$^表示所有的依赖
$^表示第一个依赖

.PHONY xxx 表示不考虑xxx是否存在，都要操作

%.0 : %.cpp
    $(cxx) $(cxxflags) $< -o $@
表示所有的.o都由.cpp生成

SRC = $(wildcard *.cpp) 表示所有的.cpp都在SCR里面
OBJ = $(patsubst %.cpp , %.o, $(SRC)) 表示替换通配符，把SRC里面所有的符合.cpp的文件替换成.o使用