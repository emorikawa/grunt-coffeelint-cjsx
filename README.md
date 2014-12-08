# grunt-coffeelint-cjsx

**Lint your CoffeeScript with CoffeeLint & React CJSX**

This uses [emorikawa/coffeelint-cjsx](https://github.com/emorikawa/coffeelint-cjsx), which is a React-specific fork of [clutchski/coffeelint](https://github.com/clutchski/coffeelint). This is for React 0.12 syntax.

## Installation

Install npm package, next to your project's `Gruntfile.js` file:

    npm install grunt-coffeelint-cjsx

Add this line to your project's `Gruntfile.js`:

    grunt.loadNpmTasks('grunt-coffeelint-cjsx');

## Options

A few additional options are supported:

### force
Type: `Boolean`
Default value: `false`

Set `force` to `true` to report CoffeeLint errors but not fail the task.

## Configuration

`coffeelint` is a multitask, so you can use it similary to `lint`, `watch` etc...

````javascript
grunt.initConfig({
    ...
    coffeelint: {
      app: ['app/*.coffee', 'scripts/*.coffee']
    },
    ...
});
````

### Options per target

````javascript
grunt.initConfig({
    ...
    coffeelint: {
      app: ['app/*.coffee', 'scripts/*.coffee'],
      tests: {
        files: {
          src: ['tests/*.coffee']
        },
        options: {
          'no_trailing_whitespace': {
            'level': 'error'
          }
        }
      }
    },
    ...
});
````

### Global - default options

````javascript
grunt.initConfig({
    ...
    coffeelint: {
      options: {
        'no_trailing_whitespace': {
          'level': 'error'
        }
      }
    },
    ...
});
````

### Loading external config

````javascript
grunt.initConfig({
    ...
    coffeelint: {
      options: {
        configFile: 'coffeelint.json'
      }
    },
    ...
});
````
Task `options` take precedence over `configFile` options.

For available options see [coffeelint homepage].

[CoffeeLint]: http://www.coffeelint.org/
[coffeelint homepage]: http://www.coffeelint.org/
