This is my personal [biome](https://biomejs.dev) configuration.  It's currently based on the 2.0 beta, as I've experienced a number of issues with recent stable 1.9 release in multi-root workplaces.  2.0beta1 seems to resolve these.


### Key features
- Uses your `.gitignore` to avoid formatting unuseful files and directories.
- Up to 100 chars per line for modern monitors.
- Double quotes, trailing commas, semicolons
- Spacing: spaces instead of tabs, 2 instead of 4

### Usage
Firstly, install [biome](https://biomejs.dev) and this [configuration](https://www.npmjs.com/package/@jszymanowski/biomejs-config):

```sh
pnpm i -D @jszymanowski/biomejs-config @biomejs/biome
```

Then add the following to your `biome.json`:

```jsonc
{
  "$schema": "https://biomejs.dev/schemas/latest/schema.json",
  "extends": ["@jszymanowski/biomejs-config"]
}
```

And finally, add the following scripts to your `package.json` to easily format and lint your code:

```jsonc
{
  "scripts": {
    "format": "biome format --write .",
    "lint": "biome check .",
    "lint:ci": "biome ci .",
    "lint:fix": "biome check --write --unsafe ."
  }
}
```