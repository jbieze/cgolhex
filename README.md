# Conway's Game of Life: Hex

Conway's Game of Life is cellular automaton devised by mathematician John Conway. It is governed by a set of rules dictating the filling or emptying of cells on a grid determined by the board's previous state. A cell that is filled is "alive", and a cell that is empty is "dead". The life or death of any given cell is based on a simple ruleset.

### The Rules

1. Any live cell with fewer than two live neighbours dies, as if caused by underpopulation.
2. Any live cell with two or three live neighbours lives on to the next generation.
3. Any live cell with more than three live neighbours dies, as if by overpopulation.
4. Any dead cell with exactly three live neighbours becomes a live cell, as if by reproduction.
[Rules](https://en.wikipedia.org/wiki/Conway's_Game_of_Life#Rules)

This project will be an alternate version of Conway's Game of Life that takes place on a hexagonal grid rather than a square one. As it has a different grid shape than the original, the rules will need to be adjusted in order for cell birth and death to happen at a rate frequent enough to prevent the cells from all dying off quickly, but still balanced enough that the board does not devolve into hexagonal chaos.

Functionality & MVP

In Conway's Game of Life: HEX, users will begin with a blank, hexagonal canvas. They will be able to interact with the board in several ways:

* Selecting specific cells to be filled at game start
* Randomly inserting a number of filled cells with a Random button
* Toggling border options (wrap / fixed)
* Starting, pausing, and resetting the automation

Wireframe

Conway's Game of Life: HEX will be on a single page with a JavaScript canvas and some control buttons at the bottom. These will include a random seeding button, border option selector, and a start/pause button.

Conway's Game of Color Wireframe

##Architecture and Technologies

This project will be implemented with the following technologies:

* Vanilla JavaScript and `jquery` for overall structure and game logic
* `HTML5 Canvas` for DOM manimpulation and rendering
* Webpack to bundle and serve up the various scripts

In addition to the webpack entry file, there will be four scripts involved in this project:

`board.js`: this script will handle the logic for creating and updating the necessary DOM elements.
`game.js`: this script will handle the logic behind the scenes. An `Automata` object will hold an array of `Cell`s. It will be responsible for doing neighbor checks for each `Cell` upon iteration and updating the `Cell` array appropriately.
`cell.js`: this lightweight script will house the constructor and update functions for the `Cell` objects. Each `Cell` will simply contain an `alive?` boolean.
`state.js`: this script will hold objects representing a (potentially randomized) state of the board.

##Implementation Timeline

**Day 1:** Setup all necessary Node modules, including getting webpack up and running and Easel.js installed. Create webpack.config.js as well as package.json. Write a basic entry file and the bare bones of all 3 scripts outlined above. Learn the basics of Easel.js. Goals for the day:

* Get a green bundle with webpack
* Learn enough Easel.js to render an object to the Canvas element

**Day 2:** Build out the Cell object to connect to the Board object. Create and render the grid. Build in the ability to toggle the live/dead states on click for each cell. Goals for the day:

* Complete the cell.js module (constructor, update functions)
* Render a grid to the Canvas using
* Make each cell in the grid clickable, toggling the state of the cell on click

**Day 3:** Create the automata logic backend. Build out modular functions for handling the different grid types along with their unique neighbor checks and rule sets. Incorporate the automata logic into the rendering. Goals for the day:

* Export a Game object with correct type and handling logic
* Have a functional grid on the Canvas frontend that correctly handles iterations from one generation of the game to the next

**Day 4:** Install the controls for the user to interact with the game. Style the frontend, making it polished and professional. Goals for the day:

* Create controls for game speed, stop, start, reset, and shape type
* Have a styled Canvas, nice looking controls and title
