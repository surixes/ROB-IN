# Installation and Run Guide

## Table of Contents

1. [Requirements](#requirements)
2. [Installation](#installation)
3. [Running](#running)
4. [Map Generation and Setting Obstacles](#map-generation-and-setting-obstacles)

## Requirements

- Python 3.12 or higher
- Dependencies from `requirements.txt` installed

## Installation

1. **Clone the repository**:

   ```bash
   git clone https://github.com/tomasrock18/rob-in.git
   ```

2. **Navigate to the project directory**:

   ```bash
   cd rob-in-main
   ```

3. **Create a virtual environment (optional)**:

   ```bash
   python -m venv venv
   source venv/bin/activate # For Linux and macOS
   venv\Scripts\activate # For Windows
   ```

4. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

## Running

```bash
python3 main.py
```

## Map Generation and Setting Obstacles

The map is represented as a two-dimensional matrix, where each cell corresponds to a specific position in the robot's movement environment. In this matrix:

- `0` — represents a free cell through which the robot can move.
- `1` — represents an obstacle (a wall) that the robot cannot pass through.

### The map generation process includes the following steps:

1. Define the map size: The height and width of the map are specified. If not provided, they are generated randomly within the range from 2 to 100.
2. Set the obstacle probability: The `wall_chance` parameter determines the probability that each cell will be an obstacle.
3. Generate the map: For each cell, it is randomly determined whether it will be free or an obstacle, based on the specified probability.
4. Define the start and end points: If not specified, the robot always starts at position `(0, 0)`, and the target position is `(height - 1, width - 1)`.

[Back to top](../../README.en.md)
