# Radix UI Themes with Tailwind

A Tailwind CSS plugin that seamlessly integrates [Radix UI Themes](https://www.radix-ui.com/themes) design tokens into your Tailwind CSS workflow. Use Radix UI's carefully crafted colors, typography, spacing, and more directly in your Tailwind classes.

## Features

- 🎨 **Full Radix UI Theme Support** - Access all Radix UI theme colors, including accent and gray scales
- 📐 **Typography System** - Use Radix UI's font sizes, line heights, letter spacing, and font families
- 📏 **Spacing System** - Leverage Radix UI's spacing scale with Tailwind utilities
- 🎯 **Border Radius** - Use Radix UI's radius tokens in your Tailwind classes
- 🌈 **Color Mapping** - Automatic mapping of common Tailwind colors to Radix UI equivalents
- ⚙️ **Flexible Configuration** - Choose between Radix UI naming or Tailwind naming conventions
- 🌓 **Dark Mode** - Built-in support for dark mode via class strategy

## Installation

Install the plugin using your preferred package manager:

```bash
pnpm install radix-ui-themes-with-tailwind -D
# or
npm install radix-ui-themes-with-tailwind -D
# or
yarn install radix-ui-themes-with-tailwind -D
```

## Usage

Add the plugin to your Tailwind CSS configuration:

```typescript
import type { Config } from "tailwindcss";
import radixThemePlugin from "radix-ui-themes-with-tailwind";

const config: Config = {
  content: [
    "./src/**/*.{js,ts,jsx,tsx}",
    // ... your content paths
  ],
  theme: {},
  plugins: [
    radixThemePlugin({
      useTailwindColorNames: true,
      useTailwindRadiusNames: true,
      mapMissingTailwindColors: true,
    }),
  ],
};

export default config;
```

## Configuration Options

The plugin accepts the following options:

### `useTailwindColorNames` (default: `true`)

When `true`, uses Tailwind's color scale naming (e.g., `50`, `100`, `200`, etc.). When `false`, uses Radix UI's numeric naming (e.g., `1`, `2`, `3`, etc.).

**Example with `useTailwindColorNames: true`:**
```html
<div class="bg-accent-500 text-accent-900">Content</div>
```

**Example with `useTailwindColorNames: false`:**
```html
<div class="bg-accent-7 text-accent-9">Content</div>
```

### `useTailwindRadiusNames` (default: `true`)

When `true`, uses Tailwind's radius naming (e.g., `xxs`, `xs`, `sm`, `md`, `lg`, `xl`). When `false`, uses Radix UI's numeric naming (e.g., `1`, `2`, `3`, etc.).

**Example with `useTailwindRadiusNames: true`:**
```html
<div class="rounded-md">Content</div>
```

**Example with `useTailwindRadiusNames: false`:**
```html
<div class="rounded-3">Content</div>
```

### `mapMissingTailwindColors` (default: `true`)

When `true`, automatically maps common Tailwind colors that don't exist in Radix UI to their closest Radix UI equivalents:
- `zinc` → `sand`
- `neutral` → `sage`
- `stone` → `mauve`
- `emerald` → `grass`
- `fuchsia` → `plum`
- `rose` → `crimson`

You can also provide a custom mapping object:

```typescript
radixThemePlugin({
  mapMissingTailwindColors: {
    zinc: "sand",
    neutral: "sage",
    // ... custom mappings
  },
})
```

## Available Utilities

### Colors

All Radix UI theme colors are available as Tailwind color utilities:

- **Accent colors**: `amber`, `blue`, `bronze`, `brown`, `crimson`, `cyan`, `gold`, `grass`, `gray`, `green`, `indigo`, `iris`, `jade`, `lime`, `mint`, `orange`, `pink`, `plum`, `purple`, `red`, `ruby`, `sage`, `sand`, `sky`, `slate`, `teal`, `tomato`, `violet`, `yellow`
- **Alpha variants**: All colors support alpha variants (e.g., `bg-accent-500A`, `text-gray-900A`)
- **Special colors**: `background`, `surface`, `overlay`, `panel`, `selection`

**Examples:**
```html
<div class="bg-accent-500 text-accent-900">Accent color</div>
<div class="bg-gray-100 text-gray-900">Gray scale</div>
<div class="bg-accent-500A/50">Alpha variant</div>
<div class="bg-surface">Surface color</div>
```

### Typography

#### Font Sizes
```html
<p class="text-xs">Extra small</p>
<p class="text-sm">Small</p>
<p class="text-base">Base</p>
<p class="text-lg">Large</p>
<p class="text-xl">Extra large</p>
<p class="text-2xl">2XL</p>
<p class="text-3xl">3XL</p>
<p class="text-4xl">4XL</p>
<p class="text-5xl">5XL</p>
```

#### Font Families
```html
<p class="font-sans">Default font</p>
<p class="font-heading">Heading font</p>
<p class="font-code">Code font</p>
<p class="font-strong">Strong font</p>
```

#### Line Heights
```html
<p class="leading-1">Line height 1</p>
<p class="leading-2">Line height 2</p>
<!-- ... up to leading-9 -->
```

#### Letter Spacing
```html
<p class="tracking-1">Letter spacing 1</p>
<p class="tracking-2">Letter spacing 2</p>
<!-- ... up to tracking-9 -->
```

### Spacing

Radix UI spacing scale is available through Tailwind's spacing utilities:

```html
<div class="p-1">Padding 1</div>
<div class="m-2">Margin 2</div>
<div class="gap-4">Gap 4</div>
<!-- ... and more -->
```

### Border Radius

```html
<div class="rounded-xxs">Extra extra small</div>
<div class="rounded-xs">Extra small</div>
<div class="rounded-sm">Small</div>
<div class="rounded-md">Medium (default)</div>
<div class="rounded-lg">Large</div>
<div class="rounded-xl">Extra large</div>
```

## Requirements

- **Tailwind CSS** ^3.3.3
- **@radix-ui/themes** ^1.1.0

## Repository

- **GitHub**: [https://github.com/needim/radix-ui-themes-with-tailwind](https://github.com/needim/radix-ui-themes-with-tailwind)
- **Issues**: [https://github.com/needim/radix-ui-themes-with-tailwind/issues](https://github.com/needim/radix-ui-themes-with-tailwind/issues)

## License

MIT

## Author

Nedim Arabacı
