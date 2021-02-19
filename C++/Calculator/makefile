CXX = g++
CXXFLAGS = -std=c++11 -Wall -pipe -O2

PROGRAM = calculator
OBJECTS = $(PROGRAM).o

.SUFFIXES: .o .cpp

.cpp.o:
	$(CXX) $(CXXFLAGS) -c -o $@ $<

all: $(PROGRAM)

$(PROGRAM): $(OBJECTS)
	$(CXX) $(CXXFLAGS) $(OBJECTS) -o $(PROGRAM)

clean:
	rm -f *.o $(PROGRAM)
