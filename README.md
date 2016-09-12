CSS Casino
===================

----------
## Background
CSS Casino is a site that demos casino-themed animations using only HTML and CSS.

----------
## MVP

With CSS Casino, users will be able to:

- [ ] Scroll through a single-page app
- [ ] Hover over the graphics to activate the animations
- [ ] Toggle to show/hide the source code for that animation

----------
## Wireframes
As a whole, this single-page app will contain a section for each of the animation categories. At the top, it will have an animation of CSS Casino in neon lettering that flashes subtly. This header will also contain a brief one-liner explaining the purpose of this site as well as links to the Github source code and my LinkedIn page.

A side navigation will be fixed to the right of the screen to hint at what section is coming up and what section was before. 

----------
## Architecture and Technologies
**NB**: one of the main things you should be researching and deciding upon while you write this proposal is what technologies you plan to use.  Identify and create a plan of attack for the major technical challenges in your project.  It's okay if you don't have all the details of implementation fleshed out, but you should have a solid roadmap by Monday morning.

This project will be implemented with the following technologies:

- Vanilla JavaScript and `jquery` for overall structure and game logic,
- `Easel.js` with `HTML5 Canvas` for DOM manipulation and rendering,
- Webpack to bundle and serve up the various scripts.

In addition to the webpack entry file, there will be three scripts involved in this project:

`board.js`: this script will handle the logic for creating and updating the necessary `Easel.js` elements and rendering them to the DOM.

`automata.js`: this script will handle the logic behind the scenes.  An Automata object will hold a `type` (hexagon, triangle, or square) and a 2D array of `Cell`s.  It will be responsible for doing neighbor checks for each `Cell` upon iteration and updating the `Cell` array appropriately.

`cell.js`: this lightweight script will house the constructor and update functions for the `Cell` objects.  Each `Cell` will contain a `type` (hexagon, triangle, or square) and an `aliveState` (`true` or `false`).

----------
## Implementation Timeline
**Monday - Day 1**: Setup basic HTML index document. Learn Canvas
all necessary Node modules, including getting webpack up and running and `Easel.js` installed.  Create `webpack.config.js` as well as `package.json`.  Write a basic entry file and the bare bones of all 3 scripts outlined above.  Learn the basics of `Easel.js`.  Goals for the day:

- Get a green bundle with `webpack`
- Learn enough `Easel.js` to render an object to the `Canvas` element

**Tuesday - Day 2**: Dedicate this day to learning the `Easel.js` API.  First, build out the `Cell` object to connect to the `Board` object.  Then, use `board.js` to create and render at least the square grid, ideally all 3 grid types.  Build in the ability to toggle the live/dead states on click for each cell.  Goals for the day:

- Complete the `cell.js` module (constructor, update functions)
- Render a square grid to the `Canvas` using `Easel.js`
- Make each cell in the grid clickable, toggling the state of the square on click
- Do the same for triangular and hexagonal grids

**Wednesday - Day 3**: Create the automata logic backend.  Build out modular functions for handling the different grid types along with their unique neighbor checks and rule sets.  Incorporate the automata logic into the `Board.js` rendering.  Goals for the day:

- Export an `Automata` object with correct type and handling logic
- Have a functional grid on the `Canvas` frontend that correctly handles iterations from one generation of the game to the next


**Thursday - Day 4**: Install the controls for the user to interact with the game.  Style the frontend, making it polished and professional.  Goals for the day:

- Create controls for game speed, stop, start, reset, and shape type
- Have a styled `Canvas`, nice looking controls and title
- If time: include buttons on the side to toggle the color scheme of the cells
