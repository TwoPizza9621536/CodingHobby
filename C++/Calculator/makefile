CXX = g++
CXXFLAGS = -v -std=c++11 -Wall -Wextra -g -pipe -O2

PROGRAM = calculator
OBJECTS = $(PROGRAM).o

.SUFFIXES: .o .cpp

.cpp.o:
	$(CXX) $(CXXFLAGS) -c $< -o $@

all: $(PROGRAM)

$(PROGRAM): $(OBJECTS)
	$(CXX) $(CXXFLAGS) $< -o $@

clean:
	rm -f *.o $(PROGRAM) *.exe
