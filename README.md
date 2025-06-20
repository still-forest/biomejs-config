This is my personal [biome](https://biomejs.dev) configuration. It's currently based on the [2.0.0 beta](https://biomejs.dev/blog/biome-v2-0-beta/), as I've experienced a number of issues with recent stable 1.9.x release in multi-root workplaces. 2.0.0-beta1 seems to resolve these.

### Key features

- Uses `.gitignore` to avoid formatting unuseful files and directories
- Up to 100 chars per line
- Spacing: spaces instead of tabs, 2 instead of 4
- JavaScript: double quotes, trailing commas, semicolons

### Usage

Firstly, install [biome](https://biomejs.dev) and this [configuration](https://www.npmjs.com/package/@still-forest/biomejs-config):

```bash
pnpm i -D --save-exact @still-forest/biomejs-config @biomejs/biome@beta
```

Then, add the following to your `biome.json`:

```json
{
  "$schema": "https://biomejs.dev/schemas/2.0.0-beta.1/schema.json",
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

### Configuration

https://biomejs.dev/guides/configure-biome/
https://biomejs.dev/guides/big-projects/#share-the-configuration
https://biomejs.dev/reference/configuration/
