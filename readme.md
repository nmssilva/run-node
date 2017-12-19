# run-node [![Build Status](https://travis-ci.org/sindresorhus/run-node.svg?branch=master)](https://travis-ci.org/sindresorhus/run-node)

> Run the Node.js binary no matter what

You can't always assume running `$ node file.js` will just work. The user might have the `node` binary in a non-standard location. They might be using a Node.js version manager like `nvm`, which is sourced in a subshell and not available from the outside. It also depends from where you're trying to run it. For example, GUI apps on macOS doesn't inherit the [`$PATH`](https://en.wikipedia.org/wiki/PATH_(variable)), so the `node` binary would not be found. Most projects that depend on Node.js just end up telling the user to manually set the full path to the `node` binary in some project specific settings. Now every project has to do this. [Ugh...](https://gist.github.com/cookrn/4015437) I prefer things to *just* work. With this module it will.

This Bash script uses some tricks to find the Node.js binary on your system and run it.

Can be used from any environment that can spawn a process (Shell, Python, Ruby, Swift, Objective-C, etc).


### npm

#### Install

```
$ npm install --save run-node
```

#### Usage

```
$ ./node_modules/.bin/run-node file.js
```

Or in an [npm run script](https://docs.npmjs.com/cli/run-script):

```json
{
	"start": "run-node file.js"
}
```

### Manually

#### Install

Download the [run-node](run-node) file:

```
$ curl -sSLO https://github.com/sindresorhus/run-node/raw/master/run-node && chmod +x run-node
```

#### Usage

```
./run-node file.js
```
### Add and edit customizable cache path and error message

The cache path and error message are defined by ```RUN_NODE_CACHE_PATH``` and ```RUN_NODE_ERROR_MSG``` respectively. To add and edit this variables add this line to ```~.bashrc``` or ```~/.bash_profile```:

```
#node-run variables
export RUN_NODE_ERROR_MSG="Custom error message"
export RUN_NODE_CACHE_PATH="/custom/path/to/cache"
```

For example:

```
#node-run variables
export RUN_NODE_ERROR_MSG="Node.js binary not found. Make sure you have installed Node.js"
export RUN_NODE_CACHE_PATH="/home/username/.node_path"
```


## Created by

- [Sindre Sorhus](https://github.com/sindresorhus)
- [Mathias Fredriksson](https://github.com/mafredri)


## License

MIT © [Sindre Sorhus](https://sindresorhus.com)
