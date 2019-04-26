# Generic Hipster Coffee

Real website of a Café coded according to provided visual design.

To build the website I have used Bootstrap 4 which I have customized with [CSS & SASS](https://github.com/hajkovakris/ghc/blob/master/src/scss/_base.scss) along with customisation using Bootstrap’s variables.

[Twig templates](https://github.com/hajkovakris/ghc/tree/master/src/templates) were used for generating HTML files.

The website is deployed using Surge.sh service at https://my-hipster-cafe.surge.sh/.

I used https://github.com/benabraham/bs4-nodejs-static as a boilerplate.

## First time installation

### Install latest [node.js](https://nodejs.org/)

### Install all packages from `package.json` locally

```shell
npm install
```

_If you’re having errors with `node-gyp`, try [installing it globally](https://github.com/nodejs/node-gyp#installation)._

## Development

To develop with automatic compilation and browser refreshing run

```shell
npm start
```

And see the result on `http://localhost:3000/`

## Build

To build everything once for production deploy (in `/dist/` folder)

This build uses all generated HTML files for _UnCSS_. If it removes something you need to keep, add and array to `ignore` option in `gulpfile.js`.  

```shell
npm run build
```

## CSS (Sass preprocessor)

`index.css` is compiled from `src/scss/index.scss` by [Sass](http://sass-lang.com/).

You don't know _Scss_ syntax or don't want to use it? Just use plain CSS in `src/scss/_base.scss`.


## HTML (Twig templates)

HTML is generated from [Twig.js](https://github.com/twigjs/twig.js/) templates (JavaScript impementation of Twig templating language) in `src/templates`.

You don't need to leverage the power of templates. You can just create plain HTML files with `*.twig` extension.  

If you don't want a template to be turned into HTML file start it with `_`. Typically these are templates used for _include_ or _extend_.

Documentation for [Twig](https://twig.symfony.com/doc/2.x/templates.html).

_Warning: [Twig.js doesn't implement 100% of Twig](https://github.com/twigjs/twig.js/wiki/Implementation-Notes)._

If you need some data to be available in all templates, use `templates/data.json` for that.


## Static files (JavaScript, images, …)

Folders and files from `/src/static/` are simply copied directly to `/dist/` folder.


### Bootstrap

I commented out Bootstrap components I didn't need in `/src/index.scss`. I case you need them, don't forget to uncomment them.

`/src/_custom-bootstrap-variables.scss` contains only customized Bootstrap variables.

See `browserslist` in `package.json` for supported browsers.


### Deployment

Uploads everything in `/dist/` folder to the server.

#### Surge.sh

I used [surge.sh](https://surge.sh) free service for that.

1. Install surge client `npm install --global surge`.
1. Run `surge` manually once in `/dist`: you will create an account with surge.sh.
1. From now on run `npm run deploy` whenever you want to publish a new version.

If you want multiple people to be able to deploy to the same domain, run `surge --add mail.your.collaborator.used.to.register.with.surge@example.com` for each.
 
