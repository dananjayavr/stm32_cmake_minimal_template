### Prerequisites

- CMake
- ARM GNU GCC Tools
- MinGW

### Initialize Project

- Generate a project using CubeMX. Use a development board and initialize all peripherals to their default mode (to generate all HAL files)

- Outisde the generated directory. Create a CMakeLists.txt and arm-none-eabi-gcc.cmake files.

- Adapt the files accordingly to the board. Pay attention to :
    - Project name
    - Src and Inc paths
    - Name of startup file
    - Name of linker file
    - Compiler definition for the chosen board / MCU

### Build project

- Create a build folder (ex. cmake-build-debug) and cd to that folder

- Run `cmake -G "MinGW Makefiles" -DCMAKE_TOOLCHAIN_FILE=../arm-none-eabi-gcc.cmake -DCMAKE_BUILD_TYPE=Debug ..`

- Then, run `cmake --build . -- -j 4`

- You should obtain .bin and .hex files for your target

### Sources

- https://dev.to/younup/cmake-on-stm32-the-beginning-3766