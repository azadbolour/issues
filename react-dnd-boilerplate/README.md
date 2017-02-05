
## Issue: React DND Boiler Plate

Trying to create a boiler plate project to run the React DND examples,
separately from the source code of React DND. So react-dnd is a 
dependency of my project. And my source only includes examples.

- Clone https://github.com/gaearon/react-hot-boilerplate.

- Rename to react-dnd-boilerplate

- npm install
  >> npm WARN deprecated minimatch@2.0.10: Please update to minimatch 
     3.0.2 or higher to avoid a RegExp DoS issue

  Ignore for now.

- npm start

- http://localhost:3000

  Hello, world.

- Just making sure the initial boilerplate works.

- Now let's copy the single dustbin dnd example.

- cd src
  mv App.js App.js.boilerplate
  mv index.js index.js.boilerplate

- cp -a ~/software/react-dnd/examples/01\ Dustbin/Single\ Target/\*.js .

- npm start # See Errorr 1 below.

- Add dependencies to package.json:

    -- "react-dnd": "^2.1.4",
    -- "react-dnd-html5-backend": "^2.1.2",

- Add dev dependecies:

    -- "babel-plugin-transform-decorators-legacy": "1.3.4",
 
- Add plugin to .babelrc

    -- "plugins": ["transform-decorators-legacy"]

- npm install

- npm start

  Started without errors.

- localhost:3000 - the page comes out blank - no errors in the console

- webpack - completed successfully

- localhost:3000 - blank page - debugger shows the bundle loaded

- At this point I am not sure how to proceed to get the single dustbin example to work. 

- Let's try a different (older) combination of webpack.cong.js and server.js, 
  using webpack-dev-server.

- Add to dev dependencies:

    -- "webpack-dev-server": "^1.12.1"

- npm install

- npm start - starts OK - but still get a blank page in the browser

- So revert back to the orginal versions.


## Errors 1

ERROR in ./src/Container.js
Module not found: Error: Cannot resolve module 'react-dnd' in /Users/azadbolour/dev/bolour/main/issues/master/react-dnd-boilerplate/src
 @ ./src/Container.js 15:16-36

ERROR in ./src/Container.js
Module not found: Error: Cannot resolve module 'react-dnd-html5-backend' in /Users/azadbolour/dev/bolour/main/issues/master/react-dnd-boilerplate/src
 @ ./src/Container.js 17:28-62

ERROR in ./src/Dustbin.js
Module build failed: SyntaxError: Decorators are not officially supported yet in 6.x pending a proposal update.
However, if you need to use them you can install the legacy decorators transform with:

npm install babel-plugin-transform-decorators-legacy --save-dev

and add the following line to your .babelrc file:

{
  "plugins": ["transform-decorators-legacy"]
}

The repo url is: https://github.com/loganfsmyth/babel-plugin-transform-decorators-legacy.


  27 |   canDrop: monitor.canDrop(),
  28 | }))
> 29 | export default class Dustbin extends Component {
     |                ^
  30 |   static propTypes = {
  31 |     connectDropTarget: PropTypes.func.isRequired,
  32 |     isOver: PropTypes.bool.isRequired,

 @ ./src/Container.js 21:15-35

ERROR in ./src/Box.js
Module build failed: SyntaxError: Decorators are not officially supported yet in 6.x pending a proposal update.
However, if you need to use them you can install the legacy decorators transform with:

npm install babel-plugin-transform-decorators-legacy --save-dev

and add the following line to your .babelrc file:

{
  "plugins": ["transform-decorators-legacy"]
}

The repo url is: https://github.com/loganfsmyth/babel-plugin-transform-decorators-legacy.


  36 |   isDragging: monitor.isDragging(),
  37 | }))
> 38 | export default class Box extends Component {
     |                ^
  39 |   static propTypes = {
  40 |     connectDragSource: PropTypes.func.isRequired,
  41 |     isDragging: PropTypes.bool.isRequired,

 @ ./src/Container.js 25:11-27
webpack: Failed to compile.





