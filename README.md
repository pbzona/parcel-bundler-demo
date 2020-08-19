# Parcel Bundler Demo

[Parcel](https://parceljs.org/) is an easy way to set up bundling so that you can use things like Babel and SCSS. It's simpler than other bundlers like Webpack and Gulp because it requires little to no setup and there's no configuration to manage.

To start using it:

1. Install Parcel as a development dependency in your project:

```
npm install -D parcel-bundler
```

2. Create a script file that imports any files you want to bundle. In this demo project, it's called `script.js` and imports the SCSS styles from the `sass/` directory.

3. Import that script into your HTML:

```html
<script defer src="script.js"></script>
```

4. Add a development script to your `package.json` file:

```json
"scripts": {
  "start": "parcel index.html",
  ...
},
```

To work on the project, run `npm start`. This will cause Parcel to create a local web server that compiles your SCSS, builds your JavaScript, and can do other things too. Rather than open the HTML file in your browser, use the `localhost` URL that Parcel provides in the terminal when this command is run.

The `index.html` file is called the "entry point" - this is where Parcel starts reading from, and all the files it bundles need to be referenced from here (directly or indirectly). For example, the HTML references the JavaScript, which references the SASS. This can be more complicated in some cases, but anything that ends up in the final site must be referenced somewhere along that chain.

5. To deploy the site, you can add another script to build it:

```json
"scripts": {
  ...
  "build": "parcel build index.html"
},
```

This will create a `dist/` directory with the built files that Parcel bundles. This directory is what you'll specify when publishing to GitHub Pages.

## What other kinds of files and data can Parcel handle?

Check out their [docs](https://parceljs.org/getting_started.html) for more info.