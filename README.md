![OG Image](https://falak-repo-og-generator.vercel.app/brand?description=Falak.me%20company%20brand%20system%20-%20shadcn%2Fui-compatible%20design%20tokens%2C%20socials%2C%20logos%2C%20fonts%2C%20and%20shared%20assets&scale=2)

## Index

- [Features](#features)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [License](#license)

## Features

- Centralized Falak.me company brand system for shared use across products and teams
- shadcn/ui-compatible design tokens and Tailwind config
- Light and dark mode CSS custom properties out of the box
- Color tokens in OKLCH, RGB, and HEX via machine-readable JSON
- Centralized company socials in a dedicated export

## Project Structure

```text
.
├── .gitignore
├── README.md
├── assets/
├── bun.lock
├── globals.css
├── index.html
├── index.ts
├── package.json
├── socials.json
├── style.css
├── tailwind.config.ts
├── tokens.json
└── tsconfig.json
```

`globals.css` is the source of truth for runtime CSS variables, and `tokens.json` is the machine-readable token reference for integrations.

## Usage

Install the package:

```sh
bun add @falakme/brand
# or
npm i @falakme/brand
```

### 1. Import CSS variables

In your app's global stylesheet:

```css
@import "@falakme/brand/globals.css";
```

This registers all `--token` custom properties for light (`:root`) and dark (`.dark`) modes.

### 2. Add the Tailwind config

```ts
import type { Config } from "tailwindcss";
import brand from "@falakme/brand/tailwind";

const config: Config = {
  ...brand,
  content: ["./src/**/*.{ts,tsx}"],
};

export default config;
```

### 3. Import tokens and socials

```ts
import { tokens, socials } from "@falakme/brand";

console.log(tokens.color.light.base.primary);
console.log(socials.company.linkedin);
```

### 4. Import assets

```ts
import logo from "@falakme/brand/assets/logo.svg";
```

## License

**Proprietary & Closed Source**

This repository and all contents, including logos, icons, and design assets, are the property of Falak.me. This is not open source. You may not copy, reproduce, distribute, modify, or create derivative works without explicit written permission.
