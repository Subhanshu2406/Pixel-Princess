# Pixel-Princess

<div align="center">

![Language](https://img.shields.io/badge/Language-C-blue.svg)
![Library](https://img.shields.io/badge/Library-RayLib-D854A2.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

</div>

A 3D grid-based puzzle game developed in C using the RayLib library. The objective is to navigate the player to a target location while avoiding intelligent, moving obstacles that actively try to block your path.

<br>

<div align="center">
  
<img src="demo.gif" alt="Pixel-Princess Gameplay Demo" width="600"/>

</div>

## ✨ Key Features

- **Fully 3D Navigable World:** Explore and move within a 10x10x10 grid, offering a true three-dimensional challenge.
- **Real-time Graphics:** Built from scratch in C with the lightweight and powerful RayLib library for all graphics, windowing, and user input.
- **Dynamic Entities:** The game engine manages real-time coordinate tracking for over 4 dynamic entities (the player, the target, and multiple obstacles).
- **Challenging Obstacle AI:** Obstacles aren't random. They use a **Breadth-First Search (BFS)** algorithm to find the optimal path to intercept and block the player.
- **Robust Logic:** A stack-based history is implemented for each obstacle to prevent them from getting stuck in infinite loops, ensuring persistent and intelligent gameplay.

## 🛠️ Technology Stack

- **Core Logic:** **C**
- **Graphics & GUI:** **RayLib** library

## 🧠 Core Logic: The Obstacle AI

The primary technical challenge in Pixel-Princess is the obstacle AI. Each obstacle independently and in real-time calculates the shortest path to the player's current position.

1.  **Pathfinding:** A **Breadth-First Search (BFS)** algorithm is implemented to explore the 3D grid, guaranteeing that the obstacle finds the most direct route to the player.
2.  **Loop Prevention:** A simple BFS can lead to obstacles getting stuck in repetitive back-and-forth movements if the player also moves. To solve this, a **stack** data structure tracks each obstacle's recent positions. If a potential next move is already in its recent history, the AI is forced to explore an alternative path, leading to more complex and less predictable behavior.

## ⚙️ Getting Started

### Prerequisites

You need to have **RayLib** installed on your system. Please follow the installation instructions for your specific operating system on the [official RayLib website](https://www.raylib.com/).

### Compilation & Execution

1.  Clone the repository:
    ```sh
    git clone [https://github.com/Subhanshu2406/Pixel-Princess.git](https://github.com/Subhanshu2406/Pixel-Princess.git)
    cd Pixel-Princess
    ```
2.  Compile the source code. The exact command may vary based on your OS, but on a Linux-based system, it would be:
    ```sh
    gcc main.c -o pixel_princess -lraylib -lGL -lm -lpthread -ldl -lrt -lX11
    ```
3.  Run the executable:
    ```sh
    ./pixel_princess
    ```

## 🎮 How to Play

- **Movement:** Use the `WASD` keys to move the player (the blue cube) around the grid.
- **Objective:** Reach the green target cube.
- **Challenge:** Avoid the red obstacle cubes, which will actively move to block you.
- **Restart:** The game can be restarted if the player is caught or wishes to try again.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Created by [Subhanshu Gupta](https://github.com/Subhanshu2406) - 2024