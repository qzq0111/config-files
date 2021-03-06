# Node.js

## General

- Give Node.js more RAM: `NODE_OPTIONS="--max-old-space-size=8096" node`
- Use [different npm module versions](https://mariosfakiolas.com/blog/install-multiple-major-versions-of-a-node-module-with-npm/) at the same time.

### Packages

## Global packages

- [evaluatory](https://github.com/darekkay/evaluatory) - Web page evaluation with a focus on accessibility
- [fixpack](https://www.npmjs.com/package/fixpack) - Sort package.json
- [grunt](https://gruntjs.com/) - Task runner
- [hexo](https://hexo.io/) - Static site generator
- [http-server](https://www.npmjs.com/package/http-server) - Local HTTP server
  - `hs --cors`
- [imagemin-cli](https://www.npmjs.com/package/imagemin-cli) - Image minifier
- [npm-check-updates](https://www.npmjs.com/package/npm-check-updates) - Upgrade package.json dependencies
- [ntl](https://www.npmjs.com/package/ntl) - List and run npm tasks
- [prettier](https://prettier.io/) - Code formatter
- [release-it](https://www.npmjs.com/package/release-it) - Automate versioning and package publishing tasks.
  - [@release-it/keep-a-changelog](https://github.com/release-it/keep-a-changelog) - Keep a Changelog plugin
- [svgexport](https://github.com/shakiba/svgexport) - SVG → PNG/JPEG vonverter

```
npm install -g evaluatory fixpack grunt-cli hexo-cli imagemin-cli npm-check-updates ntl prettier release-it @release-it/keep-a-changelog svgexport
```

## Other packages

- [alex](https://github.com/get-alex/alex) - Catch insensitive, inconsiderate writing
- [create-react-app](https://github.com/facebook/create-react-app) - React boilerplate
- [envinfo](https://github.com/tabrindle/envinfo) - Development environment report
- [gulp](https://gruntjs.com/) - Streaming build system

## npm

```bash
npm outdated                 # Show outdated packages
npm ls --depth=0             # List package versions
npm publish --access public  # Publish @scoped package
```

## node-gyp

- Installation on [Windows](https://github.com/nodejs/node-gyp#on-windows)

## npm settings

```
npm config set prefer-offline true
npm config set progress false
npm config set save-exact true
```

## yarn settings

```
yarn config set no-progress
yarn config set yarn-offline-mirror ~/AppData/Roaming/yarn-offline
yarn config set yarn-offline-mirror-pruning true
```

## Semantic Versioning

- Major.Minor.Patch
- Caret (`^`): `3.^.^`
- Tilde (`~`): `3.9.~`

## n - version manager

- [n](https://github.com/tj/n)
- [n-install](https://github.com/mklement0/n-install)

Install:

```
curl -L https://git.io/n-install | bash
```

Commands:

```bash
n                    # Output versions installed
n <version>          # Install or activate node <version>
n rm <version ...>   # Remove the given version(s)
n prune              # Remove all versions except the current version
```

## pm2

```bash
pm2 start apps.yml                  # load all apps defined in apps.yml
pm2 save                            # save process list
pm2 reload apps.yml [--update-env]  # reload all apps

pm2 list              # list all processes
pm2 monit             # monitor all processes
pm2 describe 0        # display all information about a specific process

pm2 logs [app]        # display logs
pm2 reset [process]   # reset meta data (restarted time...)

pm2 install typescript   # Add Typescript support
```

- [Update pm2](http://pm2.keymetrics.io/docs/usage/update-pm2/)

```bash
pm2 save
npm install -g pm2
pm2 update
```

- Enable [logrotate](https://github.com/keymetrics/pm2-logrotate)

```bash
pm2 install pm2-logrotate
pm2 set pm2-logrotate:max_size 1M
pm2 set pm2-logrotate:retain 50
pm2 set pm2-logrotate:rotateInterval "0 1 1 1 *"
pm2 set pm2-logrotate:workerInterval 3600
```

## create-react-app

- [Advanced Configuration](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#advanced-configuration)
- `.env` file:

```
PORT=12345
GENERATE_SOURCEMAP=false
PUBLIC_URL=.               # Build as a local project/file
```
