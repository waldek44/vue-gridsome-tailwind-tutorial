# Gridsome Tailwing Tutorial

### 1. Tworzę projekt
```
gridsome create my-gridsome-site
```

### 2. Dodaję Tailwind

1. Instaluję Tailwind
```
npm install tailwindcss
```

2. Instaluję Post CSS
```
npm i -D @fullhuman/postcss-purgecss
```

3. Tworzę *main.css* w */src* a w nim dodaję:
```
@tailwind base;

@tailwind components;

@tailwind utilities;
```

4. Na górze *main.js* dodaję mój nowy css
```
// Import global styles
require('~/main.css')
```

5. Generuję *tailwind.config.js* komendą
```
npx tailwind init
```
Wypełniam *tailwind.config.js* tym:
```
module.exports = {
    theme: {
        extend: {}
    },
    variants: {},
    plugins: []
}
```

6. Następnie do *gridsome.config.js* dodaję tailwind i pureCSS

```
const tailwind = require('tailwindcss')
const purgecss = require('@fullhuman/postcss-purgecss')

const postcssPlugins = [
  tailwind(),
]

if (process.env.NODE_ENV === 'production') postcssPlugins.push(purgecss(require('./purgecss.config.js')))

module.exports = {
    siteName: 'Gridsome',
    plugins: [],
    css: {
        loaderOptions: {
            postcss: {
                plugins: postcssPlugins,
            },
        },
    },
}
```

7. Tworzę w root plik *purgecss.config.js* a wnim :
```
module.exports = {
    content: [
        './src/**/*.vue',
        './src/**/*.js',
        './src/**/*.jsx',
        './src/**/*.html',
        './src/**/*.pug',
        './src/**/*.md',
    ],
    whitelist: [
        'body',
        'html',
        'img',
        'a',
        'g-image',
        'g-image--lazy',
        'g-image--loaded',
    ],
    extractors: [
        {
            extractor: content => content.match(/[A-z0-9-:\\/]+/g),
            extensions: ['vue', 'js', 'jsx', 'md', 'html', 'pug'],
        },
    ],
}
```

### 3. Logo + Card
Robię kartę
'tracking-wider' to letter-spacing
'h-3' to wysokość
'text-sm' pomniejszenie rozmiaru tekstu