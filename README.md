grunt-zopfli-native
====================

Compress your files with zopfli without installing anything.

[![Build Status](https://secure.travis-ci.org/pierreinglebert/grunt-zopfli-native.png)](http://travis-ci.org/pierreinglebert/grunt-zopfli-native) [![Dependency Status](https://gemnasium.com/pierreinglebert/grunt-zopfli-native.png)](https://gemnasium.com/pierreinglebert/grunt-zopfli-native)


## Installing

```shell
npm install grunt-zopfli-native --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-contrib-compress');
```

## Using

Task targets, files and options may be specified according to the grunt [Configuring tasks](http://gruntjs.com/configuring-tasks) guide.

### Options

#### mode `String`

Choose an output format, you can choose between `gzip`, `zlib` or `deflate`. Defaults to gzip.

```javascript
 zopfli({ format: 'zlib' })
 ```

#### extension `String`

Forces an extension to your files. Defaults depends on the mode chosen.

```javascript
 zopfli({ format: 'zlib' })
 ```

#### zopfliOptions `Object`

Options object to pass through to node-zopfli. See [node-zopfli documentation](https://github.com/pierreinglebert/node-zopfli#options) for more information.

```javascript
{
    verbose: false,
    verbose_more: false,
    numiterations: 15,
    blocksplitting: true,
    blocksplittinglast: false,
    blocksplittingmax: 15
};
```


### Examples

#### Make a gzip file

```js
zopfli: {
  main: {
    files: [
      {src: ['path/*'], dest: 'gzipped_files/', filter: 'isFile'}
    ]
  }
}
```

#### Compress your files for prodection
```js
zopfli: {
  main: {
    expand: true,
    cwd: 'assets/',
    src: ['**/*'],
    dest: 'public/'
  }
}
```
