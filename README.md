# Terri-Fried

Terri-Fried is a multi-platform game originally made by [PolyMars](https://github.com/PolyMarsDev) in C++ for Ludum Dare 46. </br>
This is a Terri-Fried fork, which focuses on PSV version and steady stream of updates.

## Screenshots
![](https://img.itch.zone/aW1hZ2UvNjIwMzc4LzMyOTcwNzkucG5n/347x500/tOVUPR.png) ![](https://img.itch.zone/aW1hZ2UvNjIwMzc4LzMyOTcwODAucG5n/347x500/7WajOY.png) ![](https://img.itch.zone/aW1hZ2UvNjIwMzc4LzMyOTc3NTMucG5n/347x500/OQvCg8.png) ![](https://img.itch.zone/aW1hZ2UvNjIwMzc4LzMyOTcwODMucG5n/347x500/sQhgXc.png)

## Requirements
- CMake
- C++ build tools
- [VitaSDK](https://docs.vitasdk.org)
- Git

## Compiling
### Windows
It's suggested to use Ubuntu on WSL in case of compiling on linux, it is the same as on Linux (below).
### Linux
1. Install VitaSDK via [vdpm](https://github.com/vitasdk/vdpm)
2. Clone this repository: `git clone https://github.com/przebor/Terri-Fried` and move into it: `cd Terri-Fried`
3. Generate Makefile: `cmake .`
4. Build the vita package: `make Terri-Fried.vpk`
5. Compiled Terri-Fried should be available at `Terri-Fried.vpk`
## To-Do (or rather Wanna-Do)
Literally everything you could think of:
- Scoreboard
- Multi-player of some sort (?)
- More control options
- Customization
- Settings + main menu
## Credits
Original source code - [Terri-Fried](https://github.com/PolyMarsDev/Terri-Fried)
Github Action for building - [mandar1jn's fork](https://github.com/mandar1jn/Terri-Fried)
