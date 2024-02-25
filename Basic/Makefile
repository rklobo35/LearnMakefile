## Makefile for basic program
# Variables
PROJECT_DIR = $(shell pwd)
SRC_DIR = $(PROJECT_DIR)/src
OBJ_DIR = $(PROJECT_DIR)/obj
BIN_DIR = $(PROJECT_DIR)/bin 
CC = gcc
CXX = g++
CFLAGS = -Wall -O2
CXXFLAGS = -Wall -O2 -std=c++17
LDFLAGS = -lm

#include folder
CFLAGS += -I$(PROJECT_DIR)/inc
CXXFLAGS += -I$(PROJECT_DIR)/inc

# Object files
OBJS = $(patsubst $(SRC_DIR)/%.c,$(OBJ_DIR)/%.o,$(shell find $(SRC_DIR) -name '*.c')) \
       $(patsubst $(SRC_DIR)/%.cpp,$(OBJ_DIR)/%.o,$(shell find $(SRC_DIR) -name '*.cpp'))

TARGET = bin/output

# Executable
all: create $(TARGET)

$(TARGET): $(OBJS)
	$(CXX) $(LDFLAGS) $^ -o $@

# Cleaning
clean:
	rm -rf $(OBJ_DIR) $(BIN_DIR)

# Automatic rules for object files
# (you don't need to edit these)
$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c
	$(CC) $(CFLAGS) -c $< -o $@

$(OBJ_DIR)/%.o: $(SRC_DIR)/%.cpp
	$(CXX) $(CXXFLAGS) -c $< -o $@

# Rule for creating the obj folder if it doesn't exist
create:
	mkdir -p obj bin
