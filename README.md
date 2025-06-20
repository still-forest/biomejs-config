# Biome config for Still Forest

### Key features

- Uses `.gitignore` to avoid formatting unuseful files and directories
- Up to 120 chars per line
- Spacing: spaces instead of tabs, 2 instead of 4
- JavaScript: double quotes, trailing commas, semicolons

### Usage

Firstly, install [biome](https://biomejs.dev) and this [configuration](https://www.npmjs.com/package/@still-forest/biomejs-config):

```bash
pnpm i -D --save-exact @still-forest/biomejs-config @biomejs/biome
```

Then, add the following to your `biome.json`:

```json
{
  "$schema": "https://biomejs.dev/schemas/2.0.0/schema.json",
  "extends": ["@still-forest/biomejs-config"]
}
```

And finally, add the following scripts to your `package.json` to easily format and lint your code:

```json
{
  "scripts": {
    "format": "biome format --write .",
    "lint": "biome check .",
    "lint:ci": "biome ci .",
    "lint:fix": "biome check --write --unsafe ."
  }
}
```

### Extending this config

A downstream project's `biome.json` may be extended to override or add rules to this config. Example:

```json
{
  // boilerplat config above
  "files": {
    "includes": ["**", "!**/dist/**", "!**/*.generated.js"]
  }
}
```

For more information:

- https://biomejs.dev/guides/configure-biome/
- https://biomejs.dev/guides/big-projects/#share-the-configuration
- https://biomejs.dev/reference/configuration/
