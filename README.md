[![Travis Build Status](https://travis-ci.org/mzanini/DeeMemory.svg?branch=master)](https://travis-ci.org/mzanini/DeeMemory)
[![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/8gnefkiu0lp7d2dl/branch/master?svg=true)](https://ci.appveyor.com/project/mzanini/deememory/branch/master)
[![devDependency Status](https://david-dm.org/mzanini/DeeMemory/dev-status.svg)](https://david-dm.org/mzanini/DeeMemory?type=dev)


# DeeMemory

DeeMemory is that software that every Dungeon Master always wanted to have. It is designed to provide the DM with all the information he/she needs, when they are needed. DeeMemory is designed to be world-agnostic. This means that all the specifications about the world that is played are loaded via [user-generated tables](docs/Tables.md).

Even if DeeMemory is world-agnostic, it was originally created to play DT Sanders's world, you can find out more about him in the [credits](#credits) section.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

## Running the tests

Run the tests with a simple:
```
npm run test
```
## Deployment

Build for Windows with `electron-builder`, instructions taken from [here](https://www.electron.build/multi-platform-build#docker):

1. Make sure the docker daemon is running:
    ```
    sudo systemctl start docker
    ```
2. Run docker container:

   ```
   docker run --rm -ti \
    --env-file <(env | grep -iE 'DEBUG|NODE_|ELECTRON_|YARN_|NPM_|CI|CIRCLE|TRAVIS_TAG|TRAVIS|TRAVIS_REPO_|TRAVIS_BUILD_|TRAVIS_BRANCH|TRAVIS_PULL_REQUEST_|APPVEYOR_|CSC_|GH_|GITHUB_|BT_|AWS_|STRIP|BUILD_') \
    --env ELECTRON_CACHE="/root/.cache/electron" \
    --env ELECTRON_BUILDER_CACHE="/root/.cache/electron-builder" \
    -v ${PWD}:/project \
    -v ${PWD##*/}-node-modules:/project/node_modules \
    -v ~/.cache/electron:/root/.cache/electron \
    -v ~/.cache/electron-builder:/root/.cache/electron-builder \
    electronuserland/builder:wine
   ```

3. Type in `yarn && yarn distWin`

## Built With

* [Electron](http://electron.atom.io/)
* [Webpack](https://webpack.github.io/)
* [React](https://facebook.github.io/react/)
* [Docker](https://www.docker.com/)

## Authors

* **Marco Zanini** - *Initial work* - [Personal website](https://www.marcozanini.it)

## Credits
This project would have never started if it would have not been for DT Sanders. Ted is a long-standing Dungeon Master, science fiction and fantasy author, ex-navy officer. In his spare time he is an Aerospace System Engineer. During multiple nights spent playing Ted's personal D&D world and rolling die, we were wondering if we could create a software that would alleviate part of the DM's most repetitive work like rolling encounters and non-playing characters. This is when DeeMemory was born, from Ted's requirements and Marco's technical abilities.

If you want to know more about Ted, check out [his personal website](http://www.dtsanders.com/about-sanders/), where you can also download some of his stories for free! His books can be found [here](https://www.amazon.com/D-T-Sanders/e/B015NI7XSK).

If you want to know more about Marco, [here](https://www.marcozanini.it) you can find his personal website, where you can find many other links to his different personalities.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
