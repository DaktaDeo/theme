# Multipass

This repository acts as a community forum for [Multipass](https://daktadeo.be/multipass) questions, feature ideas, and bug reports. To start a thread, please open an [issue](https://github.com/DaktaDeo/Multipass/issues).

The code is not the code of the app, but the code of the website. The code of the app is not open source. 

Please note that this theme is solely dedicated for the `multipass.rocks` website and isn't meant to be used as a content-neutral theme. It does **not** follow semver and may contain hard-coded logic specific to the Multipass documentation.


## Development Setup

This repo can be developed on its own since it is a self-contained VitePress theme. Make sure to use [pnpm](https://pnpm.io/) as the package manager when installing deps. A demo app is available in `/demo` and can be run with `npm run dev`:

```bash
$ pnpm install
$ npm run dev
```

## Developing with Real Content

To work on this theme in the context of the `vuejs.org` website requires cloning both repos and linking the theme into the docs repo:

1. Clone repositories:

   ```bash
   git clone git@github.com:daktadeo/multipass-docs.git
   git clone git@github.com:daktadeo/theme.git
   ```

2. Link theme into docs repo:

   ```bash
   # In ./theme
   pnpm install
   # Make @vue/theme available for global linking
   pnpm link --global

   # in ./docs
   pnpm install
   # Link theme
   pnpm link --global @daktadeo/theme
   ```

3. Start VitePress server:

   ```bash
   # in ./docs
   pnpm run dev
   ```

### Available Scripts

Here is the list of available scripts that can be used during the development.

```bash
# Boot local dev server.
$ npm run dev

# Build demo, then serve locally. This is for testing
# production build in the local environment.
$ npm run serve

# Run lint via Prettier.
$ npm run lint

# Run type check via tsc.
$ npm run type
```

## License

[MIT](http://opensource.org/licenses/MIT)

Copyright (c) 2021-present Evan You
Copyright (c) 2023-present Veerle Deschepper, DaktaDeo

## Credits
- based on https://github.com/vuejs/theme
