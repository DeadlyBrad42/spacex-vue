# spacex-vue
### A project using Vue.js, by Brad Mason

## Viewing the Project
### Running Locally
To run the project for the first time, pull it down & run `npm install` & then `npm start`. Once the dependencies are installed, subsequent runs can just use `npm start`.

## Project Structure
The project was an exploration in learning how to use _Vue.js_ with Single File Components. The **App Component** current does most of the heavy lifting, by framing out the structure of the page, `fetch`ing the data from the API, and messaging the data into a more usable format.

To keep things simple, the App Component is comprised of a **Toolbox Component** and **Launch Manifest Component**. The Toolbox Component handles user input & redirects the events back up to the App Component to be used to compute the `filteredLaunches`, which the Launch Manifest Component takes and displays.

## Future Developments
As this was my first Vue.js project, there are several changes I'd like to explore for future developments:
* Moving the logic out of the App Component. I'd like to explore using a cleaner repository pattern here rather than hardcoding the API & filter options.
* I would like to research alternative ways to define datamodels & validate the data passing through components. Since I am not (yet!) too familiar with Vue.js, I opted to not stray far from the beaten path, but I would be interested to use it with something like TypeScript's strongly-typed classes, or even find other third-party vanilla-JavaScript solutions.
