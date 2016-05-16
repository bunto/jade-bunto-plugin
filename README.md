jade-bunto-plugin
=================

Converter Plugin that brings Jade support to the [Bunto blog-aware, static site generator](https://bunto.github.io/).

## HOWTO

 1. Install Jade with NPM. e.g. `$ npm install jade -g`
 1. Place the `jade.rb` file into your Bunto installation under `_plugins/` 
 1. All static pages and posts ending in the extension `.jade` are now processed through Jade automatically.
 1. Layouts need special treatment, see below.

## Applying Jade to Layouts

Unfortunately Bunto doesn't yet allow plugins to pre-process layout files before further processing.  To write your layouts in Jade, you therefore have to render them externally.  Fortunately this only needs to be done frequently for a small period of time, during layout development.

During layout development, we recommend:

 1. Create a `_layouts/jade/` folder where you will place your "pre-rendered" Jade source.
 2. Create a `Makefile` or shell script to execute the Jade compile-and-watch command: `jade -w -o ../ *.jade`
 3. In another terminal, simultaneously run your Bunto builds: e.g. `bunto serve -w`

## License

See [LICENSE](https://github.com/bunto/jade-bunto-plugin/blob/master/LICENSE).

