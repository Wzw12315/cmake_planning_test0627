# Project Background

## Overview
This is a C++ planning system project built with CMake. The project currently serves as a basic framework or test project for path navigation and planning functionality.

## Project Structure
- **Main Program**: `planning_main.cpp` - Entry point that initializes and runs the planning process
- **Process Module**: 
  - `process.h/cpp` - Handles the main planning process flow
  - Depends on PNC_Map module
- **PNC_Map Module**:
  - `pnc_map.h/cpp` - Intended for path navigation and map related functionality
  - Currently implements basic test output only

## Current State
- The project is in early development stage
- Core modules are defined but functionality is minimal
- Main execution flow: main → Process → PNC_Map
- Uses C++17 standard

## Development Notes
- The project is built with CMake 3.29.0
- Executables are output to `/bin` directory
- Simple module structure with clear dependencies
