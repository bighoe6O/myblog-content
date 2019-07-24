Title:  drum-tabs_g++
Date:   2018-01-16 23:36:03 +0100
Category: Dev
Tags: MAO, Dev, Rythmes


```
make
g++ -Wall  -g -c src/drumtab-parser.cpp -o obj/drumtab-parser.o
src/drumtab-parser.cpp: In member function ‘void DrumTabParser::print_bytes(std::vector<int>)’:
src/drumtab-parser.cpp:103:7: warning: ‘auto’ changes meaning in C++11; please remove it [-Wc++0x-compat]
   for(auto it = steps.begin(); it != steps.end(); ++it) {
       ^
src/drumtab-parser.
cpp:103:12: error: ‘it’ does not name a type
   for(auto it = steps.begin(); it != steps.end(); ++it) {
```

https://gcc.gnu.org/projects/cxx-status.html#cxx11

```make
CXXFLAGS = -std=c++11
```
