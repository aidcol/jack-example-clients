# Makefile for JACK audio development on macOS
CXX = clang++
CXXFLAGS = -std=c++17 -Wall -O3 -ffast-math
INCLUDES = $(shell pkg-config --cflags jack)
LIBS = $(shell pkg-config --libs jack)

# Add math library
LIBS += -lm

# Real-time optimization flags
CXXFLAGS += -DNDEBUG -march=native -mtune=native

# Target executable
TARGET = simple_client.exe
SOURCES = simple_client.cpp

# Default target
all: $(TARGET)

$(TARGET): $(SOURCES)
	$(CXX) $(CXXFLAGS) $(INCLUDES) -o $(TARGET) $(SOURCES) $(LIBS)

clean:
	rm -f $(TARGET)

.PHONY: all clean
