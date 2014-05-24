biojs-core
==========

Sandbox for the BioJS MSA Viewer with AMD and CoffeeScript

### Step 1) Embed components

Have a look at the [quick start examples](https://cdn.rawgit.com/greenify/biojs-msa-amd/master/development.html).

```
<script src="biojs.js"></script>
<link type="text/css" rel="stylesheet" href="css/msa.css" />
```

This library is [AMD-compatible](#), so you can also embedd it with an AMD loader of your choice.

The whole API is coming soon.

### Step 2) Developing 

[`development.html`](https://cdn.rawgit.com/greenify/biojs-msa-amd/master/development.html)

* all javascript modules are loaded on demand
* CoffeeScript is compiled by the Browser

All source files are located in `js`

* If you write a module in CoffeeScript, use `.coffee` as an extension and prefix the module with `cs!`
* Apart from dependencies you need to add your new module to the `main.js` (otherwise it won't be bundles into the single file)

Have fun coding.

### Step 3) Compiling


* all sources are bundled to one JS file (`build/biojs.js`)
* CoffeeScript is compiled by R.js
* `biojs.js` gets minified
* two versions of the documentation are generated (with and without AMD loader)
* static files (`css`, `samples`) + third party `libs` are copied to `build`
* a Javascript API documentation is generated (coming soon)

```
python3 build.py
```


You might need install the Python module `lxml`, therefore run
```
pip3 install lxml 
```

### Just building biojs.js

Maybe you don't have python installed, here are some solutions how you could call the `r.js` compiler


with Node:
```
node js/libs/r.js -o build.js
```

with Java:
```
java -classpath jars/rhino.jar:jars/compiler.jar org.mozilla.javascript.tools.shell.Main js/libs/r.js -o build.js
```

### Documentation

1) [`prod_amd.html`](#)
users has an AMD loader (RequireJS). BioJS is loaded as a AMD dependency.
 
2) [`prod_non_amd.html`](#)
users has no AMD loader. BioJS automatically uses almond and registers as global variable


### Used libraries

* [coffeescript](https://github.com/jashkenas/coffee-script)
* [require.js](https://github.com/jrburke/requirejs)
* [require-cs](https://raw.githubusercontent.com/jrburke/require-cs/latest/cs.js)
* [r.js](https://github.com/jrburke/r.js/)
* [almond](https://github.com/jrburke/almond)

### Used libraries for the documentation

* [jQuery](https://jquery.com/)
* [highlight.js](http://highlightjs.org/)
* [Bootstrap](http://getbootstrap.com)