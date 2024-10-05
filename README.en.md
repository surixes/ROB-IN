[![ru](https://img.shields.io/badge/lang-ru-blue.svg)](README.md)

# ROB-IN

A small script demonstrating the A-Star algorithm for finding the shortest path.

## Table of Contents

1. [Navigation System Description](docs/en/navigation-system-description.md)
2. [Installation and Setup Guide](docs/en/installation-and-setup-guide.md)
3. [User Guide](docs/en/user-manual.md)
4. [Technical Details](docs/en/technical-details.md)
5. [Examples and Use Cases](docs/en/examples-and-use-cases.md)
6. [License](LICENSE)

## Installation

_Python 3.12 is required for proper installation_

```shell
git clone https://github.com/surixes/ROB-IN.git
cd rob-in-main
pip install -r requirements.txt
```

## Running

```shell
python3 main.py
```

This command will generate a random map and attempt to apply the pathfinding algorithm. If no path is found, the program will display the map without a route. To rerun, close the qt window and run the above command again. (Alternatively, you can open the script in any preferred IDE.)

### Function Descriptions

This solution implements 4 functions:

1. `generate_map` - Creates a map with obstacles.
2. `heuristic` - Calculates the heuristic between two points.
3. `find_path` - Implements the A-Star algorithm on the given map.
4. `optimize_path` - Optimizes the given route.

### Usage Examples

```python3
# Creates a map of random size with a 30% chance of obstacles appearing
map = generate_map()

# Similarly, but the number of rows in the map matrix will be set to the specified value, in this case 100
map = generate_map(100)

# Map with specified dimensions but still a 30% chance of obstacles
map = generate_map(100, 100)

# Map with specified dimensions but with double the probability of obstacles appearing
map = generate_map(100, 100, 0.6)
```

```python3
# Initially, this was a lambda function, but PyCharm didn't like it, so it was separated out
delta = heuristic((0, 0), (5, 5))
```

```python3
# Pass the map and get the path. The start and end points are set by default.
path = find_path(map)

# The same, but now we specify where to start
path = find_path(map, (10, 10))

# And now also specify the end point
path = find_path(map, (10, 10), (0, 0))
```

## Support

If you have questions, concerns, or find an error in the documentation, you can contact the following contacts::

- Email: support@example.com
- Telegram: @example

[Back to top](README.en.md)
